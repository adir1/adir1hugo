---
title: 'Your Data Is Safe&hellip;&hellip; Not!!!'
author: Adi R
type: post
date: 2009-05-11T05:47:07+00:00
url: /2009/05/your-data-is-safe-not/
categories:
  - General
tags:
  - computer science
  - Windows Vista

---
<p align="justify">
  Poor attempt at a Not joke? I had a rough day, but I want to promptly document it for everyone’s benefit. Our story begins during late night hours, somewhere deep in the tough Ulduar area in World of Warcraft Instance.
</p>

<p align="justify">
  My computer suddenly hung, though mouse was still moving, which is highly unusual! After simple troubleshooting failed to recover it, I proceeded to a full power-cycle. World of Warcraft promptly crashed again, much quicker this time, with CRC error. Concerned, I scheduled a full HD check-disk and surface scan, and left it overnight.
</p>

<p align="justify">
  In the morning, I found situation to be same or worse. Software was crashing left and right, seemingly randomly. World of Warcraft’s handy Repair utility, told me my installation was “Too Corrupt to Repair”. I tried many different things, at first focusing on Hard-drive integrity, and kept finding pretty much all data written to disk, coming back with CRC errors.
</p>

<p align="justify">
  <img style="border-bottom: 0px; border-left: 0px; margin: 0px 0px 0px 10px; display: inline; border-top: 0px; border-right: 0px" title="Computing Today" border="0" alt="Computing Today" align="right" src="https://i2.wp.com/www.adir1.com/uploads/2009/05/computingtoday.png?resize=204%2C97" width="204" height="97" data-recalc-dims="1" />Long story short, I recalled a handy memtest utility right on the boot menu of <a href="http://www.ubuntu.com/" target="_blank">Ubuntu</a>. I ran it, and voila, my screen quickly filled with Lots of RED errors, thousands, in fact. I proceeded to remove all memory modules (I had four DDR2), and put them one by one to the test, and as Murphy would have it, the last module was the faulty one. All others passed long battery of tests with flying colors. I reinstalled the three good memory modules, and computer is back to normal, as if nothing was wrong!
</p>

<p align="justify">
  Moral of the story? I see several here – For example, why didn’t self-respecting Vista OS (ahem, funny!) include some sanity checks, to alert me to memory failures, instead of crashing with blue screens and failing “Host Processes”? (Yea, I know there is <a href="http://en.wikipedia.org/wiki/Dynamic_random_access_memory#Errors_and_error_correction" target="_blank">ECC memory</a>, but I am not sure it would have helped in this strange scenario).
</p>

<p align="justify">
  But even more so, what about Cloud? I had <a href="https://www.mesh.com/welcome/default.aspx" target="_blank">Mesh</a> and <a href="http://sync.live.com" target="_blank">Live Sync</a> going! Something may have Synched into the cloud, with corruption on it! Any <a href="http://www.mozy.com" target="_blank">Cloud Backup</a>, and pretty much everything else, would cause a disaster! Amazon’s entire <a href="http://aws.amazon.com/s3/faqs/" target="_blank">S3</a> cluster went down not too long ago, due to corruption in status data being passed around the cloud.
</p>

<p align="justify">
  I’ve been long excited about <a href="http://opensolaris.org/os/community/zfs/whatis/" target="_blank">ZFS technology</a>, and while I am sure it would have alerted me to problems sooner, I am not certain it could have prevented real data corruption in this case. With faulty memory module, everything written from memory to disk, will most likely become “corrupt for life”. Even an attempt to rescue such data will likely not end well, unless hard-drive is moved to another computer for rescue.
</p>

<p align="justify">
  It seems that as computer scientists we are missing this very fundamental issue. We can’t trust our latest operating system to alert us if our underlying hardware is misbehaving?! And that our files are becoming corrupt every time we touch them?!
</p>

<p align="justify">
  Back to the drawing board!
</p>