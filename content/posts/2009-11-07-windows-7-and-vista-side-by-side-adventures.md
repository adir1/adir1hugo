---
title: Windows 7 and Vista Side by Side Adventures
author: Adi R
type: post
date: 2009-11-07T19:47:03+00:00
url: /2009/11/windows-7-and-vista-side-by-side-adventures/
categories:
  - General
tags:
  - Windows

---
<p align="justify">
  It was really straight forward to setup side-by-side Windows 7 and Vista on the same computer, simply put them on separate hard-drives (either physical or separate partitions). Installation was no troubles, and I was happily booting between them back and forth as needed, until I hit a snag last night, MAJOR SNAG!!!
</p>

<p align="justify">
  I guess Vista didn’t shut down properly or something, so in the next reboot into Windows 7 it detected problems on my Vista hard-drive and decided to “Fix It”. I was not really concerned, since Windows 7 surely knows how to read/fix Vista partition &#8212; OR DOES IT!? An unsettling “Replacing invalid security id with default security id for file” messages popped up, and kept going for thousands of files.
</p>

<p align="justify">
  Long story short, after it finished, Windows 7 gave me “Access Denied” error when trying to view Vista drive, and even Vista itself couldn’t boot &#8212; just goes into black screen. So much for thinking that Win 7 chkdsk was smart enough to not break Vista partition.
</p>

<p align="justify">
  Well, here is how I managed to dig myself out of this, and it wasn’t easy! Boot into Windows 7, right click on the Vista drive (E:\ in my case), and choose Security. First, you need to change Ownership to something public, I decided to change it to “Everyone”. Apply that ownership to all sub-dirs/objects also, obviously. Once you take ownership. Click on Security tab and reset that also, again, I did Everyone Full Control and added Guest full control. Not super secure, of course, but that is old partition I am transitioning away from, so I gather it’s good enough. Voila, after that everything is fine. Although, I did notice that if I “push” files from Vista into Win 7 file system, sometimes they come out with “funny” security. It was just one occurrence, but…
</p>

<p align="justify">
  Overall I am still loving Win 7, it’s fast and stable, but I guess I should accelerate my transition away from Vista.
</p>