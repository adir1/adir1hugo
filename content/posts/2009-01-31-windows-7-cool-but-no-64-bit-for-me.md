---
title: Windows 7 – Cool, but no 64 Bit for me?
author: Adi R
type: post
date: 2009-01-31T21:15:57+00:00
url: /2009/01/windows-7-cool-but-no-64-bit-for-me/
tags:
  - Microsoft
  - Technology
  - Windows

---
<p align="justify">
  I think as any responsible techie, I downloaded both 32 Bit and 64 Bit editions of Windows 7 beta, the first day it came out (naturally). Got 2 keys also (one for each edition).
</p>

<p align="justify">
  <a href="/uploads/2009/01/screenshot-clear.jpg" target="_blank"><img title="screenshot_clear" style="border-right: 0px; border-top: 0px; display: inline; margin: 0px 0px 0px 10px; border-left: 0px; border-bottom: 0px" height="152" alt="screenshot_clear" src="/uploads/2009/01/screenshot-clear.jpg?resize=240%2C152" width="240" align="right" border="0" data-recalc-dims="1" /></a> Shortly thereafter I installed 32 Bit version, on 2 very different computers. One was old Athlon 64 processor, 1gb ram, barely alive computer that my daughter insists that she still likes. The other was good Quad Core system. The new optimizations really shine, as old Athlon 64 computer felt as snappy as the new shiny quad core system! My daughter loves it now, and discovered several favorite features already, like that rotating desktop wallpaper (kitties galore!) and the sticky notes on the desktop. Most software she tried so far, worked properly and performed very well! We hit few minor bugs, but it’s beta after all, so we promptly reported them.
</p>

<p align="justify">
  In light of this positive experience, I finally got the courage to install 64 Bit version of Win 7 on my Primary computer with 4gb of Ram, as dual boot, of course. However, most strange thing happened, sad thing, annoying thing or even Disturbing thing.
</p>

<p align="justify">
  DVD with 64 Bit Windows 7 booted fine, though seem to take longer to reach first screen than I remembered on other installations. And from there, it only got worse. Win 7 Setup took 10 or 15 minutes between each “installation” step, and on screens where I had to type something, I would press a button and see it reflected on screen only 20 seconds later.
</p>

<p align="justify">
  7 Hours later, it was still on First install step!!! Though, it wasn’t stuck, you could see percentages going up, I think it was as high as 80% by then, so I left it running overnight.
</p>

<p align="justify">
  In the morning, the whole computer was completely “Off”, for whatever reason. Trying to boot into Win 7 (which now appeared on dual-boot menu), did nothing, just black screen. Safe startup mode was no help, hanging at some driver that didn’t seem related to my hardware…
</p>

<p align="justify">
  I didn’t give up, wiped that partition and tried again… After second time, I gave up.
</p>

<p align="justify">
  Strangest thing is that I don’t even know how to report this to MS. They have crashes and Feedback reported from within Windows 7, everywhere. But what if it is a case like mine, where Installer doesn’t even work?! I wonder if there is some log somewhere.
</p>

<p align="justify">
  Another strange thing is that Windows Vista and Ubuntu work flawlessly on that same computer. Go figure…
</p>

<p align="justify">
  But, it’s beta, so I am not holding it against folks at Redmond. I’ll keep trying to figure out how to submit a Setup log or something like it, in hopes that they will find time to analyze this issue.
</p>

<p align="justify">
  Final words on Windows 7 – I think it is critical that in these hard times Microsoft prices Windows 7 properly. It should be cheaper, have LESS “editions” and allow for multi-PC license for home (like Mac does!).
</p>

## Comments

### Comment by Blake Coverett on 2009-02-02 02:02:41 -0500
Sounds like the same problem I had &#8211; I tracked it down to flawed support for my SATA attached DVD drive. Everything installed perfectly off a USB DVD drive, and when I submitted a bug report about it with details about my hardware they got back to me within a day confirming my guess. They promised it would be corrected by the RC release.

### Comment by Adi R on 2009-02-02 14:33:15 -0500
Thanks for the input!

Actually, my DVD drive is IDE, but the Hard-drive where I was trying to install OS is SATA, so this explains things a lot.

Hmm, I do have a second hard-drive in that PC, connected over IDE also, as I recall. I may try it, or will wait for RC, whichever comes first (since I need to clear 20gb space, and that old drive is rather small).

### Comment by Chris on 2009-02-02 14:49:18 -0500
I had the same problem with 64 bit version taking a long time to install. I was installing on brand new hard disks and have no intention of dual booting. The installation screens seem to take about 10 minutes each. I also have SATA drives and IDE, so if it is the SATA hopefully it is fixed. The SATA I&#8217;m actually doing RAID so installed the Vista version of the RAID drivers and Win 7 picked it up fine (just took a long time to get to). Anyways my point is that 64 bit installation seems to take forever when it shouldn&#8217;t. 

AMD Phenom II quad 3ghz, 8GB RAM, (2) 150 GB 10k RPM drives.

The other problem I had was using System Restore within the Win 7 GUI. i.e. If using System Restore from the installation DVD/USB it works fine, however within the Win 7 gui it never stops loading.

3rdly &#8211; Microsoft should have included support for mounting ISO&#8217;s in Windows 7. Looking for a ISO mount software is what caused me to have to use System Restore.

PS> Send Feed back I wished worked.

### Comment by Adi R on 2009-02-02 20:58:28 -0500
Interesting idea there with Vista drivers. I wonder if I can force it to use Vista drivers during the Setup step. I recall there used to be &#8220;load custom drivers&#8221; option there, when choosing destination drive for install.

I guess I should also add some details about my platform. I am on MSI P6N Platinum motherboard (nForce 650i) with Q6600 core 2 quad processor. 4Gb DDR2 ram, but I think I mentioned that.  
Granted this platform isn&#8217;t the latest, but I really expected the quad core to last for a while, so looking forward to MS fixing this annoying issue in RC.

I&#8217;ll keep this post updated if anything further uncovered on this, keep the great comments coming!

### Comment by Adi R on 2009-02-02 21:00:15 -0500
PS: I did read somewhere that mounting ISO&#8217;s was supported in Win 7. Or perhaps it was general comment of &#8220;using virtual mounted drives&#8221;, but unclear what format file is supported for the &#8220;virtual drive&#8221;.

### Comment by John N on 2009-02-03 00:57:56 -0500
Win 7 supports *.VHD for mounting, which stands for Virtual Hard Drive. Seems akin to a .DMG (Disk Image) file in Mac OS X.

There will probably be a tool to convert ISO->VHD in no time.