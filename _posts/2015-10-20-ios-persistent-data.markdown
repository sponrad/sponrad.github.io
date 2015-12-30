---
layout: post
title:  "How I Got Persistent Data in iOS with Swift"
date:   2015-10-20 
categories: ios swift
comments: true
---

I have been working on an iOS app called Flash Force over the past few months and one of the biggest problems I had to overcome right away was how to get small bits of data to persist for a user across all their devices and across uninstall/reinstalls of the app.

The best way I discovered is to store the data in the [Keychain](https://developer.apple.com/library/mac/documentation/Security/Conceptual/keychainServConcepts/01introduction/introduction.html) (which is typically used to store passwords and keys). Apple provides Keychain use free of charge to both developers and users and the same Keychain is accessible by a user from any of their devices at any time. And users cannot directly edit Keychain values themselves.

Storing values in Keychain is simple with the helper functions provided in [Keychain-Swift](https://github.com/exchangegroup/keychain-swift). Without a helper library the built-in API is many more lines of code.

All you have to do is plop the main swift file from that repository into your project and you can start getting and setting Keychain values with something like this:

{% highlight swift %}
keychain.set("hello world", forKey: "my key")

keychain.get("my key")
{% endhighlight %}

Bear in mind that "keychain" will be the name of whatever you named the file and function.

Testing for if a keychain value has been set looks something like this:
{% highlight swift %}
if let result = keychain.get("my key") {
    //this will only fire if a value has been set to the result variable
    print(result)
  }
{% endhighlight %}

Values for one keychain entry can be cleared with ```keychain.delete("my key")```.

You can clear all of the values with ```keychain.clear()```, very helpful while testing and for some functionality in apps.

I have been using the Keychain to:

* Storing generated user ids for a user that I can use to identify them across devices
* Storing whether or not users have redeemed "Free" functionality in the app

The Keychain has been hugely helpful since the other alternatives were a lot more involved. I was debating requiring users to create acounts and log in and store all of their data on our on server, which is a huge amount of up front and on-going work.