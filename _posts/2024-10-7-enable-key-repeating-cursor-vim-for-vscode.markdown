---
layout: post
title:  "Enable Key-Repeating for Cursor editor and VSCodeVim"
date:   2024-10-07
categories: talk
comments: true
---

Exactly the same as [the regular MacOS instructions](https://github.com/VSCodeVim/Vim?tab=readme-ov-file#mac), but you need to use the Cursor bundle identifier instead of VSCode.

{% highlight bash %}
mdls -name kMDItemCFBundleIdentifier /Applications/Cursor.app
# com.todesktop.230313mzl4w4u92
{% endhighlight %}

To enable key-repeating, execute the following in your Terminal, log out and back in, and then restart VS Code:

{% highlight bash %}
defaults write com.todesktop.230313mzl4w4u92 ApplePressAndHoldEnabled -bool false
defaults delete -g ApplePressAndHoldEnabled
{% endhighlight %}

I use this with [VSCodeVim](https://vspacecode.github.io/) via [VSpaceCode](https://vspacecode.github.io/) (the spotty but excellent Spacemacs port to VSCode that I can't live without right now).
