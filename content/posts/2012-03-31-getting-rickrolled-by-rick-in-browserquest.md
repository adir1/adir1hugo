---
title: Getting Rickrolled by Rick in BrowserQuest
author: Adi R
type: post
date: 2012-03-31T19:36:48+00:00
url: /2012/03/getting-rickrolled-by-rick-in-browserquest/
tags:
  - FireFox
  - Programming
  - Weekend Fun

---
<p align="justify">
  <a href="http://browserquest.mozilla.org/" target="_blank"><img style="background-image: none; border-bottom: 0px; border-left: 0px; margin: 0px 0px 0px 10px; padding-left: 0px; padding-right: 0px; display: inline; float: right; border-top: 0px; border-right: 0px; padding-top: 0px" title="rick in browserquest photoshopped" border="0" alt="rick in browserquest photoshopped" align="right" src="https://i0.wp.com/www.adir1.com/uploads/2012/03/rick-in-browserquest-photoshopped.png?resize=195%2C229" width="195" height="229" data-recalc-dims="1" /></a>This one is definitely filed away under Weekend Fun! Kudos to <a title="Blog post about BrowserQuest release" href="http://hacks.mozilla.org/2012/03/browserquest/" target="_blank">Mozilla</a> foundation, though a bit sad that it doesn’t play on iPad (and some other browsers) yet.
</p>

<p align="justify">
  The brilliance of the <a href="http://browserquest.mozilla.org/" target="_blank">BrowserQuest</a> is not just in it’s grand fun gameplay, but also that it is truly and completely <a href="https://github.com/mozilla/BrowserQuest" target="_blank">open-source</a>!
</p>

<p align="justify">
  After my son played through 19 of the 20 possible achievements in about 19 minutes, we set out to find the elusive 20th achievement, which is unlisted. Well, as a responsible father (and because it is tons of fun), I set out to find the last one using the source code! The code itself is brilliantly simple. I am really looking forward to promised official post about the architecture, but meanwhile it is easy to see that the entire thing is running on NodeJS server, using BiSON, WebSockets and written in JavaScript and HTML5.
</p>

<p align="justify">
  Although it took me only about a minute to track the last achievement down, and figure out that an NPC named Rick is who I need, finding him proved illusive. Even though I had coordinates of the dude from world map definition JSON, it’s really tricky to track him down as game use teleports when doors are opened, to shift you to new area, as I gathered.
</p>

<p align="justify">
  So after about an hour of math and checking different door/portal/methods/logic, I just got annoyed and did a quick Google! And voila, of course someone already posted it on our beloved <a href="http://gaming.stackexchange.com/questions/59442/what-are-the-two-hidden-achievements-and-how-do-i-get-them" target="_blank">StackOverflow (for Gaming)</a>. There you have it – complete fun experience with hidden achievements FTW !!! Next? Just clone the <a href="https://github.com/mozilla/BrowserQuest" target="_blank">GitHub repo</a> and set of on your own adventure, of <strong>making a browser game</strong>!!!
</p>

## Comments

### Comment by manuel on 2012-04-01 13:16:36 -0500
cheers, finally all quests solved!