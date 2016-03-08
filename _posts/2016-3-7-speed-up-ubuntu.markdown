---
layout: post
title:  "Speed Up Ubuntu and Make it Usable"
date:   2016-3-7
categories: talk
comments: true
---

###Quick commands to make some speed happen:

    sudo echo vm.swappiness=15 >> /etc/sysctl.conf
    sudo echo vm.vfs_cache_pressure=50 >> /etc/sysctl.conf
    sudo apt-get install preload

###Explanation and rant for those who care

Something that really bothers me about a fresh of install of Ubuntu is that it is always SO SLOW compared to Mac OS or Windows on the same hardware. The two commercial products are very optimized out of the box and it makes them really pleasant to work with. 

When I hit the Windows key or Apple-Space I want to see the start menu and Spotlight IMMEDIATELY and it makes sense for the command I entered to be responded to at a high priority by the OS. Same goes for opening programs, switching tabs, and closing programs. Unresponsiveness is frustrating.

The experience in Ubuntu is just not there out of the box, I found a few quick fixes for this that actually make a huge difference.

###Swappiness

The swappiness value controls how readily the OS will place running software into 'swap' memory on the hard disk, removing it from ram. The closer to zero this value is, the less and less likely programs will be placed into hard drive memory. Ubuntu ships with a value of 60 and I get great results in the 15 range on my old laptop.

###VFS Cache

The VFS Cache setting does something along the lines of deterring storing stuff in hard drive swap, sounds a little similar to swappiness to me. *I DON'T FULLY UNDERSTAND THIS ONE BUT IT FEELS RIGHT.*

###Preload

Preload is software that runs in the background and stores your most often used programs into memory for quick access. This one may be the most important. One thing to note is that "software" affects almost every corner of the linux OS and in general makes everything snappier. It requires zero customization and makes a huge difference in how fast things run.

###Thanks

Please let me know if you have any other speed up tips that don't involve compiling my own kernel and rewriting drivers, ain't got time for that!