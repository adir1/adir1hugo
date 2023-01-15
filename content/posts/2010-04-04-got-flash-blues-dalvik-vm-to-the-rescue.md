---
title: Got Flash Blues? Dalvik VM to the Rescue!
author: Adi R
type: post
date: 2010-04-04T20:22:27+00:00
url: /2010/04/got-flash-blues-dalvik-vm-to-the-rescue/
tags:
  - Adobe Flash
  - Android
  - Google
  - Java
  - Open Source

---
<p align="justify">
  <a href="http://www.adobe.com/flashplatform/" target="_blank">Adobe Flash Platform</a> got some bad press lately, and its exclusion from iPad is a major slap in the face to Adobe by <a href="http://gizmodo.com/5475005/steve-jobs-flash-video-would-make-the-ipad-battery-life-15-hours" target="_blank">Steve Jobs</a> himself. Even though millions of sites out there (including this one) use Flash to liven up things and provide extra interactivity, Apple is willing to leave users to stare at <a href="http://www.engadget.com/2010/01/27/apples-ipad-keeping-adobe-flash-away-from-your-couch/" target="_blank">Big Empty Boxes on iPad</a>, rather than add Flash support.
</p>

<p align="justify">
  <img style="border-right-width: 0px; margin: 5px 0px 5px 10px; display: inline; border-top-width: 0px; border-bottom-width: 0px; border-left-width: 0px" title="Android Logo" border="0" alt="Android Logo" align="right" src="/uploads/2010/04/AndroidLogo.png?resize=170%2C202" width="170" height="202" data-recalc-dims="1" /> To be fair, I myself did a lot of Flash/Flex development and still do! I really like what ActionScript can achieve, much more so than messing with JavaScript and CSS/HTML. But, times are tough, so here is my proposal:
</p>

<p align="justify">
  How about we setup an Open Source project to build Flash alternative based on <a href="http://www.dalvikvm.com/" target="_blank">Dalvik VM</a> and some existing Android platform components. We already know that it’s very capable, and if Google is true to its mantra, they wouldn’t mind sharing! Why not reuse the great UI library and 3D API’s, and others, and bring them into the browsers on all platforms – Windows, Unix and of course, Mac and iPad/iPhone! Can’t we all just get along?! Plus with <a href="http://groups.google.com/group/0xlab-devel/browse_thread/thread/1edef26f4e5b7427?pli=1" target="_blank">JIT for Dalvik</a>, and potential for native hardware video acceleration on Windows/Mac/Ubuntu/Handsets, I see very bright future!
</p>

<p align="justify">
  I am not ignoring <a href="http://www.silverlight.net/" target="_blank">Silverlight</a> or <a href="http://en.wikipedia.org/wiki/HTML5" target="_blank">HTML 5</a>, I just don’t see either as viable solution. Silverlight is still proprietary and you need specific Microsoft tools to develop for it, while HTML 5 feels like a bit “future-ware” and even when materializes, it’s unclear that it can provide all the richness of visual effects, 3D support, overall speed and pixel level manipulation which we expect in this day and age.
</p>

<p align="justify">
  But what about <a href="http://javafx.com/" target="_blank">JavaFX</a> you ask? Feels like DOA to me, sadly. I love Java, which is yet another reason why I think Android approach is great, but JavaFX is just “overweight” out the door, and many posted about other major shortcomings.
</p>

<p align="justify">
  Plus true modularity is still not there with neither technology! Why are we (developers) still forcing users to go through complex installation ritual to get new software on a system? Why does it have to be a gamble, especially when installing complex applications, whether it will interfere with other applications on the system and break things?!
</p>

<p align="justify">
  So, I want to see comments! I know it’s rather big project, so without some people weighing in as to it’s merit (or with offers of participation), I am not going to bother starting even. Besides, probably Googlers are already doing it, whether in their 20% or even as main task, who knows&#8230;
</p>

<p align="justify">
  <strong>UPDATE</strong>: I just discovered that someone implemented Flash player in JavaScript!? I didn’t think it was possible, but it is seemingly done using HTML5 browser features in modern browsers. More details and browsers compatibility list on the <a href="http://wiki.github.com/tobeytailor/gordon/" target="_blank">Gordon project on Github</a>.
</p>