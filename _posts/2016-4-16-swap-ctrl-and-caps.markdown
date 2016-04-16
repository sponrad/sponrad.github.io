---
layout: post
title:  "Linux Map Caps Lock to Control"
date:   2016-4-16
categories: talk
comments: true
---

I like to swap Caps Lock with Control on laptops. (easier copy pasting, browser tabs, Emacs, etc.)

I installed Manjaro KDE and there does not seem to be a setting for it so I found this and just want to keep it handy for copy-pasting.

{% highlight bash %}
xmodmap -e "remove Lock = Caps_Lock"
xmodmap -e "keysym Caps_Lock = Control_L"
xmodmap -e "add Control = Control_L"
{% endhighlight %}

One line:
{% highlight bash %}
xmodmap -e "remove Lock = Caps_Lock" && xmodmap -e "keysym Caps_Lock = Control_L" && xmodmap -e "add Control = Control_L"
{% endhighlight %}