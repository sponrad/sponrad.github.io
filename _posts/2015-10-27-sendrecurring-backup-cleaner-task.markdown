---
layout: post
title:  "Reliability with Cleanup Crew Backup Tasks"
date:   2015-10-27
categories: talk
comments: true
---

I have run a service called SendRecurring for several years now. The premise of it is that users setup reminders (text or email) and they are sent at the pattern interval they want. My goal has been to get scheduling accurate to the minute.

However as the service has become more popular and received more traffic it has been difficult to stay within the 1 minute standard. Highly popular times such as at the beginning of the work day and end of the work day on the east coast were starting to begin to creep outside of the 1 minute range. This was because the server was queuing up all of the emails that need to go out at a certain time and looping through them, sending each one, and re-scheduling them etc, all in one process.

I solved this initial buildup problem a ways back by sending all of the reminders that are due to go out to task queues that can be dispatched by multiple processes if need be. Extra instances can be spun up and used to send out emails etc. This has largely solved the 1 minute error.. however, other problems have risen.

Problem
-------
For some reason I do not know (maybe due to multithreading) some emails will slip through the cracks occassionally. It is frustrating. An email that slips through the cracks would not send and would not update its next send time... so it would be lost in limbo until the user noticed and corrected its schedule. Or emailed me to do it. Not ideal for anyone!


Solution
--------
The solution I came up with to solve this is a special task that plays the role of "cleanup crew". I created a second cron job that trails behind the main cron job by a gap and catches the reminders that were not sent at the time they were supposed to. Currently, I am using a trailing time of about 10 minutes while this is new, but as I becoe more confident in the system I may tighten the gap for less delay for the caught emails. Already the results have been great.

I made sure to turn on logging for anything that the cleanup crew catches and it has been extremely helpful in finding those one-off reminders that fail to send, and also some very old reminders that had had issues.