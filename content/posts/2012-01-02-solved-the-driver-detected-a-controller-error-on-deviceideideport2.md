---
title: 'Solved: The driver detected a controller error on \Device\Ide\IdePort2'
author: Adi R
type: post
date: 2012-01-02T07:53:09+00:00
url: /2012/01/solved-the-driver-detected-a-controller-error-on-deviceideideport2/
tags:
  - Microsoft
  - Technology
  - Windows

---
<p align="justify">
  <a class="thickbox" href="http://answers.microsoft.com/en-us/windows/forum/windows_vista-hardware/atapi-event-id11-the-driver-detected-a-controller/7fdd47da-7c86-4f7b-bdf7-096bb4f059f4" target="_blank"><img style="background-image: none; border-bottom: 0px; border-left: 0px; margin: 0px 0px 5px 10px; padding-left: 0px; padding-right: 0px; display: inline; float: right; border-top: 0px; border-right: 0px; padding-top: 0px" title="Microsoft Answers Picture" border="0" alt="Microsoft Answers Picture" align="right" src="https://i1.wp.com/www.adir1.com/uploads/2012/01/Microsoft-Answers-Picture.png?resize=244%2C155" width="244" height="155" data-recalc-dims="1" /></a>My son and I went through rather painful ordeal with this Event 11 that Windows quietly generates. It took us few weeks to fully work out why Windows suddenly started hanging, misbehaving or even crashing with blue screen. Now that I feel it is fully resolved, I thought I’d share my conclusion (and the process) – hopefully it will help few others out there who are struggling with this. Ridiculously, many people are likely affected by this issue, but unless they open Event Viewer and search for this event id 11, they will not realize that hanging is not “normal” behavior, even for Windows! OS seems to silently recover from this problem 10 to 60 seconds later, which is really strange in my book – considering that user isn’t even alerted to this serious atapi error.
</p>

<p align="justify">
  For impatient souls among us, here are my conclusions:
</p>

  * <div align="justify">
      First thing – check the SATA/EIDE and power cable connection between your hard-drive and the motherboard. If possible, try another SATA outlet on motherboard or another SATA cable if available.
    </div>

  * <div align="justify">
      If it still happens, the bad news is that this is likely a disk controller error, which is especially problematic since nowadays disk controllers are built into the Motherboard. If you are in a budget crunch, one potential workaround is to <a href="http://answers.microsoft.com/en-us/windows/forum/windows_vista-hardware/atapi-event-id11-the-driver-detected-a-controller/7fdd47da-7c86-4f7b-bdf7-096bb4f059f4" target="_blank">slow down your HD to use different PIO</a>. This may avoid hangs, but will slow overall performance, so no fun solution…
    </div>

  * <div align="justify">
      Proper solution appears to be to replace motherboard, hence replacing disk controller. There are many motherboards starting at just $50 and in most cases it will improve overall performance and stability for you, even if you keep the same CPU and other components.
    </div>

<p align="justify">
  I am pretty confident that this is the right diagnosis, as we went through a lot of trial and error investigative work, in a space of few weeks, after it started abruptly. At first, I was pretty much convinced that HD is dying. The system had two hard-drives, and the older hard-drive was seemingly working just fine, even with the same SATA cable and connected to the same slot on the Motherboard. Turns out it was using slower PIO by virtue of it being older HDD. During the troubleshooting process I reinstalled fresh Windows 7 64 Bit multiple times, on various HD drives, only to see the issue start happening almost instantly after clean install. Few days ago a fresh HDD became available (separate long story), so I tried replacing the “dying” HD. Guess what, it being newer HD, it was instantly affected by the same issue, even though I put clean Windows there also. Thus it was concluded that controller was faulty, and I went shopping for a new motherboard. As an aside – DDR3 memory is Ridiculously Cheap. I was able to pick up 8 GB of Gamer grade memory for $25 (after rebate), so that is another bonus with upgrade.
</p>

<p align="justify">
  We ended up replacing CPU also (time for upgrade anyhow), but all other components stayed the same. Right now I have 3 Hard-drives happily working flawlessly there, including the “dying” HD, and the rest of the computer is faster and better than ever.
</p>

<p align="justify">
  Feel free to leave comments if you are still struggling with this issue, and I will try to answer. Good Luck and <strong>Happy New Year</strong>!
</p>

<p align="justify">
  <strong><u>PS</u></strong>: As a bonus tip – while I was troubleshooting, I had to reinstall Windows 7 couple of times on various HD drives. Did you know you can avoid “tarnishing” your license in such scenario by Skipping product key page during Windows 7 setup? Very handy, and then you have up to 28 days to put your real key in and activate. During that period Windows is fully functional and we had used it like that for over a week while troubleshooting.
</p>

## Comments

### Comment by Mick on 2012-01-14 17:40:31 -0500
I am also experiencing the exact same issues as you were and I dont believe its my hard drive either. 

Event Viewer reports &#8220;Atapi &#8211; Event ID 11 &#8211; Driver detected a controller error on \Device\Ide\IdePort0&#8221;. 

Have done all the usual troubleshooting as you would expect. I have just switched the SATA cable to Port1 as all errors seem to happen on Port0.

Seems to be OK for just now but I&#8217;m not holding my breath, very strange fault, can easily be mis-diagnosed however I do agree with yourself on the controller as being the fault.

Just need to give it time now and see how it goes.

### Comment by Adi R on 2012-01-15 13:03:56 -0500
You are on the right track, but this one is super nasty issue, sorry.  
I just had it start happening on our Laptop also, but seems to only occur few times a week at most.  
I reviewed all connections, they seemed fine. Next step was to run diagnostic from manufacturer (WD in this case), which reported SMART info was good but there are some bad sectors. So I ran full check & repair of Bad sectors, took few hours and found 3 corrupt files and some bad sectors. Still, going forward this should improve things, I&#8217;ll report back on that.

### Comment by Andre Santiago on 2012-02-18 12:13:08 -0500
Although this issue seems to be silent for awhile the latest windows update brought it to its knees. Really sucks. I will follow the suggestions here to see what happens

### Comment by Kevin on 2012-03-06 17:23:24 -0500
I have been dealing with this same problem and have checked everything and I to believe its the MB. I did install ubuntu and it does run better but instead of hanging for 10-20 seconds it just locks up when I try to do too much at once or randomly on its own. I even bought a new HDD yesterday as I thought for sure it was that. I knew it had to be a hardware issue because i had Win7 running fine for a few years.

Back to ubuntu until I can save for a new MB/RAM/CPU, my current MB is 6 years old so I think I am due anyways.

Thanks for sharing&#8230;

### Comment by Kelly on 2012-03-30 03:38:27 -0500
Hi, just 2 days ago till now, i got this same error. But instead of port 0 its port 2. &#8220;The driver detected a controller error on \Device\Ide\IdePort2&#8221;. I checked my Device Manager, there is no port 2. What should I do?

### Comment by Adi R on 2012-03-30 12:47:35 -0500
Port number changes just from the way your Hard-drive(s) is connected to the motherboard. I think maybe this post can help explain how to map between the number and the Hard-disk (look at photos especially), but if you have only one (most common), then there is no reason to check that part.  
<a href="http://www.sevenforums.com/installation-setup/193909-sata-port-numbers-vs-assignemnt-disk-numbers.html" rel="nofollow ugc">http://www.sevenforums.com/installation-setup/193909-sata-port-numbers-vs-assignemnt-disk-numbers.html</a>

Recently our laptop started acting up the same way. I checked and saw that it has Western-Digital Hard-drive, and went to their support site to download free utility. It&#8217;s not easy to use, as for best use you need to burn it to it&#8217;s own CD-R, but it literally Fixed the problem for us. It found HDD head-misalignment and after running for about an hour, it was able to repair it. Unfortunately it came back about a month later, but same process repaired it again. I am watching it carefully and will replace it if it happens one more time.

### Comment by Adi R on 2012-05-13 15:00:20 -0500
Since this post is still very popular, and because I went through 2 more hard-drive since then, here&#8217;s what I want to add:  
Statistically, Hard-drive failure is Most Likely scenario in this case. So first of all go to HD manufacturer site and download utility to check true underlaying health of your hard-drive. For me in several cases the utility correctly identified HD failures also, which resulted in warranty replacement of Hard-drive and being back to work with no errors within a week or two.

### Comment by JOhn on 2012-06-01 13:35:04 -0500
YOur motherboards are just fine, go into control panel &#8211; system and security- power managment, and set &#8220;Turn off hard disk after(Never)&#8221;, and turn off sleep fuction as well.

what&#8217;s happening is the harddisk is being turnoffed and not being turned back on. It&#8217;s a problem with windows, not your motherboard or hard disk.

### Comment by Adi R on 2012-06-04 09:18:02 -0500
There&#8217;s no harm in trying the tip above from John I doubt it will help you much. The reason is that if your Hard-Drive is not turning back On, it is also a sign of impending HD death, or perhaps a sign of faulty motherboard mechanism.  
Still, as mentioned earlier &#8211; for most folks motherboard is fine and the culprit will be hard-drive that is getting old and about to fail.  
Since I posted that article I have seen the same error on multiple other computers, and in all cases root cause was hard-drive that is acting up with Misaligned HEAD and/or excessive bad-clusters. Most of these drives were under warranty and once replaced by manufacturer, the problems disappeared.

### Comment by Brad on 2012-06-08 01:58:50 -0500
I hate to say this but we have a radio station and our broadcast machine just got this error. The machine has been running hot for a few weeks but we didn&#8217;t think anything of it. About an hour ago we noticed it was off the air, when we returned to the studio to check it we had a black screen.

I had assumed the issue was because it got stuck in sleep mode. After restarting the machine a few times, I thought to check the event log. Sure enough we received the error &#8220;The driver detected a controller error on \Device\Ide\IdePort0&#8221;, after a close review we also got one for each HD in the machine (there are 5), and a &#8220;disk&#8221; error for each one as well. I don&#8217;t know if the issue is the HDD&#8217;s, I surely hope not because that means we our out all of that data. 

Any help you can provide us will be extremely helpful. I am just worried about losing data. And this error literally came out of no where. We had assumed it overheated.

Brad

### Comment by Adi R on 2012-06-08 03:03:53 -0500
Sorry to hear there are troubles. Heat itself is most likely caused by something else, such as faulty fan on the computer case (pretty cheap to replace). Heat can cause HDD to fail early, which is likely what you are seeing.  
If you don&#8217;t feel comfortable opening computer case and figuring out what is causing the heat, I would recommend taking it to technician to address the heat issue first. Once that is addressed, diagnostic utility for Hard-drive will help figure out what is going on with it. These are available free from manufacturers web-sites, if you know the brand, or generic HDD utilities are available from download.com.  
One more thing &#8211; best not to operate the computer if it overheats. Also, once you figure out hard-drive health, you can use same utilities to save whatever data is on there.

### Comment by Robert Shell on 2012-07-21 17:45:20 -0500
Is there a test for the hard drive controller?

### Comment by Adi R on 2012-07-22 10:44:53 -0500
Robert &#8211; That is an excellent question! I have never heard of such a thing, but perhaps it does exist out there somewhere. The utilities I tried from the Shareware/Free space are Ashampoo HDD Control 2 (Free to try, but can be a bit &#8216;spammy&#8217; &#8211; <a href="http://download.cnet.com/Ashampoo-HDD-Control/3000-2086_4-10929035.html" rel="nofollow ugc">http://download.cnet.com/Ashampoo-HDD-Control/3000-2086_4-10929035.html</a>) and HDD Scan (free &#8211; <a href="http://hddscan.com/" rel="nofollow ugc">http://hddscan.com/</a>). They don&#8217;t claim to check the controller&#8230;  
Best PC diagnostic suite I am familiar with is SiSoft Sandra (free to try with large number of totally free diagnostic modules: <a href="http://download.cnet.com/SiSoftware-Sandra/3000-2086_4-10556571.html" rel="nofollow ugc">http://download.cnet.com/SiSoftware-Sandra/3000-2086_4-10556571.html</a>). It tests for very many things, so also worth a try to see what it says for you.  
If you are into free software on Linux, like several commenters were, I would recommend ZFS, which is part of an excellent FreeBSD distribution. It will provide extra logical data integrity layer above controller, so will alert you on the spot about how your integrity is fairing.

### Comment by Seculla on 2012-08-09 17:44:05 -0500
It&#8217;s the stupid SATA cables.  
The old IDE cables are superior to this new stuff.  
Stupid idiots in the IT&#8230;.

I myself and 3 of my friends have this problem, and it is the cables&#8230;

### Comment by sebastian on 2012-08-13 14:20:17 -0500
Suscribed

### Comment by hekomi on 2012-10-15 14:57:22 -0500
Solved!! 

I had same problem, took me ages to find this post among all (adding &#8220;solved&#8221; to the error message in google was a success lol) and now I can confess that after re-attaching the sata cables correctly from my ssd to the mb seems to have made the Event 11 error disappear. It used to appear 2-5 times a minute and now I have not seen it once since last reboot.

Im so happy!

### Comment by Jerry on 2012-11-30 11:25:09 -0500
Thanks guys I have the same error with my 6 year old desktop, hope its just the cable.  
I&#8217;ll try replacing the sata tomm&#8230;

### Comment by Asad on 2012-12-10 00:09:32 -0500
Hi Adi,

I just wanted to thank you very much for posting this solution.  
The intermittent hangs/freezes of 10-60 seconds were driving me nuts over the last month.  
I will not eve try to describe all the other stuff I tried.  
Anyway, the issue was resolved by plugging SATA cable into a different port on the motherboard.

Once again, thank you very much!!!

### Comment by Adi R on 2012-12-10 09:14:22 -0500
Glad to hear it helped &#8211; Great idea to plug it into a different port on MB !

### Comment by DigDeep on 2012-12-28 14:20:21 -0500
I had this problem too. for a long time.

I tried different sata cables, but it didnt help. Then I switched cables, used dvd cable for HD, and HD cable for dvd writer. 🙂 To be sure, I checked if device is getting enough power. Then I plugged sata cable for dvd device to a different port.

After that I was able to write to cd, dvd, and able to delete rewritable cd.

( I left HD on the same port!, but hard disk can also cause this error, I think, So you should try different sata port for hard disk too. (BTW this can cause BSOD or some different errors.) If anyone have multiple hard disks, make sure to check boot order is correct(bios) after changing ports. And it also not good to change hard disk to different port, where controller manufacturer is different. (btw I once did that, changed it from Marvell, to normal ICH9 SATA controller, and everything was fine, but I dont recommend it.) So normally everything should be fine, if you change port for hard drive.

<a href="http://forums.anandtech.com/showthread.php?t=2237591" rel="nofollow ugc">http://forums.anandtech.com/showthread.php?t=2237591</a>

In my case it seems that problem was not in cables, but in the faulty motherboard SATA port.

I have one question:  
Now I have dvd device on sata port 3, and Hard drive on sata port 6.  
Does this have any impact on performance?? I think it doesnt, but im not sure.

### Comment by Adi Rabinovich on 2012-12-28 16:06:06 -0500
Thanks for great comment! There should be no performance hit on that. Sometimes older motherboards will have some mix of sata ][ ports and sata ]|[ ports. It could be that port is sata 2 now, but most likely so is your hard-drive &#8211; and either way that ridiculously fast sata 3 is only relevant for newest SSD drives.