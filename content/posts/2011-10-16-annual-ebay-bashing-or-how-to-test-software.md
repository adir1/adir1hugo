---
title: Annual eBay Bashing – or Mini How-To for Large Software Base
author: Adi R
type: post
date: 2011-10-16T06:37:42+00:00
url: /2011/10/annual-ebay-bashing-or-how-to-test-software/
tags:
  - Consumerism
  - eBay

---
<p align="justify">
  <a href="http://www.ebay.com"><img style="background-image: none; border-bottom: 0px; border-left: 0px; margin: 5px 0px 5px 10px; padding-left: 0px; padding-right: 0px; display: inline; float: right; border-top: 0px; border-right: 0px; padding-top: 0px" title="eBay Logo" border="0" alt="eBay Logo" align="right" src="https://i2.wp.com/www.adir1.com/uploads/2011/10/eBay-Logo.png?resize=120%2C76" width="120" height="76" data-recalc-dims="1" /></a>I fondly call my wife lately Commodity Investor, as she loves to scout out best deals on eBay. In fact, I would easily bet that we are in their top 10% of customers list, and let’s just leave it at that. So why is it that they allow themselves to continuously upset us?
</p>

<p align="justify">
  Granted, some of the occurrences are not their fault – try as they might, bad sellers are still abound there. I understand that it is really hard to figure out who is lying, the buyer with years of track records of purchases, or seller who joined few weeks ago and got no solid feedbacks yet.
</p>

<p align="justify">
  But this post is not about that, it is instead all about things that are Completely within eBay Inc’s control, or at least they ought to be. Here are just two of more Fun bugs for this week, that are live on their Production site:
</p>

  * <div align="justify">
      My eBay – Whoever asked them to do Ajax on the items list, the developers must have looked back and said Huh, is that like “Food” item? They are completely clueless how to implement it properly, paging is just awful, printing completely broken, going to see item and coming back is broken.
    </div>

  * <div align="justify">
      eBay Search – This is funny, because clearly this is a different team and implemented “list” technology completely differently. They have complete reverse of the above bug – if you do navigate to second page, but then switch category, your new category list starts with Second page!!!
    </div>

<p align="justify">
  Seriously, we aren’t even trying to discuss how far the website look & feel is from anything resembling modern web. Instead, we are talking basic functionality here, leading to people being unable to view properly the Items people paying Money to display and sell. The sad part? I am sure they employ a small army of developers and testers.
</p>

<p align="justify">
  In fact, I am here to say that the bigger the team gets – the harder it is to maintain consistency or quality. So what can we learn here? Here are some constructive tips for our brethren at eBay IT :
</p>

  * <div align="justify">
      Hire a Small group of HIGH Quality developers (yea, expensive ones) to develop and design core Infrastructure for the site, Including UI Components and their “glue platform”.
    </div>

  * <div align="justify">
      Once that core platform is ready, unleash the rest of your developers to customize, reuse, enhance and repurpose it across all eBay Inc properties. Yes, that does mean that My eBay and eBay Stores and other eBay Lists will share the same components – that’s a Good Thing!
    </div>

  * <div align="justify">
      Create a LOT of automated tests, including ones that Render page and look at it to reflect that it functions as expected. There are plenty of frameworks for this. Still, after these automated tests, there is No Substitute for High Quality live testers, the ones who notice things with usability also, beyond plain “ugly” bugs (like my wife, who finds these things weekly).
    </div>

<p align="justify">
  Okay, end of annual eBay Rant – you can return to your regularly scheduled mediocrity. Oh yea, and feel free to shop on Amazon more, their site is still behind times, but still light-years ahead of eBay, and they also offer slightly used items on their marketplace <img style="border-bottom-style: none; border-left-style: none; border-top-style: none; border-right-style: none" class="wlEmoticon wlEmoticon-smile" alt="Smile" src="https://i2.wp.com/www.adir1.com/uploads/2011/10/wlEmoticon-smile.png" data-recalc-dims="1" />
</p>