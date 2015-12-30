---
layout: post
title:  "Engineering an Unlimited plan is Impossible"
date:   2015-12-25
categories: talk
comments: true
---

I am getting rid of my Unlimited account plans and here is why.

On some Sunday in spring of 2015 I got into a conversation with someone and we started talking about a site I run called [SendRecurring](http://www.sendrecurring.com). SendRecurring is a service that lets people schedule recurring emails and texts for reminding and to ping servers and who knows what else. This person was excited to see it so I pulled out my phone and navigated to the page only to be greeted with.... some error message from my Appengine hosting that the site is unavailable.

This was a seriously bad moment for me because first off the site had never had this happen before, and also it was timed right when I was about to show it off to someone. Talk about caught with my pants down! I quickly explained to them that something was wrong and darted up to my laptop to diagnose the problem.

It didn't take long to find it. Some derelict customer had ordered an Unlimited plan and used it to send **29.5 GB** of email message body data before my quota for that hit and froze the site. This is a huge amount, equivalent to millions and millions of emails.

This is wildly out of the ordinary for the service, most days I use about 0.003 GB of that specific metric so about 0.01% of available quota.

To top it all off this customer's card payment passed at first but failed later so I didn't even get that payment. I sent them an email explaining the situation and never heard back, I think they were spammers.

###And Again...

So fast forward to December 2015. Same things happens. **Site outage** for a few hours and I get some angry emails from customers, and fires to put out. I look into the issue and it is a near perfect repeat: crazy absurd use of the unlimited plan, complete with card failing to charge.

###Action

My good customers that order the Unlimited plan, and continue to pay each month, send between 500 and 3,000 emails per month. There really is no reason for me to continue to expose the site to the vulnerabilities that come with offering an unlimited plan when most good users are so far below *unlimited*.

No matter how beefy I make my servers, an Unlimited plan can eventually be overrun, whether it is due to actually maxing out hardware and pre-set quotas, or until the bank account it is linked to is overdrawn. Not worth the risk.

I am normally operating within 1% of my quota... why even offer the chance to max out my site?

So...

I am changing the Unlimited plan to something like 10,000 and calling it good for a while.

**I recommend anyone who runs a SaaS to not include an Unlimited plan since they are impossible to engineer.**
