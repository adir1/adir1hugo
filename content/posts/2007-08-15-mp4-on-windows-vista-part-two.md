---
title: MP4 on Windows Vista – Part Two
author: Adi R
type: post
date: 2007-08-16T04:17:42+00:00
url: /2007/08/mp4-on-windows-vista-part-two/
tags:
  - h.264
  - Media Center
  - Technology
  - Windows

---
I am still struggling with exact instructions on creating not just any old MP4 file, but one that is XBOX 360 compatible. It turns out to be very very hard, for unknown reason. I&#8217;ve emailed <a target="_blank" href="http://www.majornelson.com">Major Nelson</a> from <a target="_blank" href="http://www.xbox.com">XBox</a> at Microsoft, but so far he&#8217;s busy, obviously.

I did manage to create MP4 files from my media, which play fine using <a target="_blank" href="http://www.videolan.org/vlc/">VLC</a> and <a target="_blank" href="http://www.apple.com/quicktime/">QuickTime</a> players, but I wanted them to play inside Vista Media Center. And, it turned out to be not as hard as it sounds, so just follow these simple steps to success (should work just as well for Windows XP Media Center, though I haven&#8217;t had a chance to try it there yet):

  1. Set Windows Vista Restore Point, in case something goes Awry. Simply Right-Click on your Computer (on Desktop or Start-Menu), and select Properties. Then, choose System Protection under Tasks. Finally click the Create button, at the bottom (just above Ok/Cancel buttons). Name your Restore Point and it should be created in no time.
  2. Download and Install <a target="_blank" href="http://haali.cs.msu.ru/mkv/">Haali Media Splitter</a> (aka Matroska Splitter) download link on the right there.
  3. Download and Install latest beta bundle of <a target="_blank" href="http://www.afterdawn.com/software/video_software/codecs_and_filters/ffdshow.cfm">FFDShow</a> software. Make sure to grab the beta, which is more Vista compatible (**unlike** latest stable).
  4. Almost done! Now, you just need to tell Media Center that it&#8217;s ok to include MP4 files. Open RegEdit for this, and find and adjust the following key:  
        [**HKEY\_CLASSES\_ROOT**.mp4]  
        &#8220;PerceivedType&#8221;=&#8221;video&#8221;

That should be it. You can also make Explorer work with these files, simply right click on one of your MP4 files, select Open With, and point to your Windows Media Player. Make sure to mark &#8216;Always use selected program to open this file type&#8217;.

If something goes wrong, or some program that used to work misbehaves after these steps, you can always go back to System Restore and restore your Backup point created in step 1.

<a atomicselection="true" href="https://i2.wp.com/www.adir1.com//uploads/2007/08/megui-h.264-codec-mini.jpg"><img border="0" align="right" width="300" src="https://i2.wp.com/www.adir1.com//uploads/2007/08/megui-h.264-codec-mini-thumb.jpg?resize=300%2C236" alt="meGUI H.264 codec mini" height="236" style="margin: 0px 0px 0px 5px; border: 0px" data-recalc-dims="1" /></a>Meanwhile, I am continuing my struggle to find best/easiest/most compatible method of  creating MP4 files. I have expanded beyond Windows (Vista or XP) and into Linux (Ubuntu actually), but thus far still no satisfactory solution found. The image, to the right of here is a small sample of H.264 codec options. Just PART of **Single** folder, out of **4** total folders!  
Easy, right???

If I ever figure it out, I will sure post the explanation here 🙂

Meanwhile, make sure to enjoy Shared Links on the right, which are updated daily, often every few hours!

**UPDATE**:  I installed Haali Media Splitter on the new Windows Vista Basic that we got with new Vostro computer (more on that later) and it cause IE 7 to start to crash on it. Of course I had restore point, but be forewarned.

## Comments

### Comment by Ilan on 2008-05-17 15:29:48 -0500
you&#8217;re awesome. I&#8217;ve been looking all over for this.

### Comment by Adi R on 2008-05-17 17:21:23 -0500
Thanks for kind words! That&#8217;s always welcome 🙂

Another easy way to play MP4 on your Vista is to download Microsoft Zune software. You don&#8217;t need Zune to make it run, it is just like Media player, only more user friendly and plays MP4s full screen.

Just surf over to Zune.net and find Zune Software download at the bottom