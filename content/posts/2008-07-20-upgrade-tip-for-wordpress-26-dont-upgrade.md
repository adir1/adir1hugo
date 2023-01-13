---
title: Upgrade Tip for WordPress 2.6 – Don’t Upgrade!
author: Adi R
type: post
date: 2008-07-21T04:15:37+00:00
url: /2008/07/upgrade-tip-for-wordpress-26-dont-upgrade/
tags:
  - WordPress
  - Technology

---
I just spent most of today upgrading to WordPress 2.6 platform, which is powering my site.

<p align="justify">
  Our exciting new features are&#8230;&#8230; well, there aren&#8217;t many new features actually. The big change is that I scrapped Categories completely, in favor of Tag Cloud based approach. Now, under each Post title are relevant Tags instead.
</p>

<p align="justify">
  The 10 minute upgrade took most of the day. Considering I was still on 2.3 or so, issues were expected, but this image upload issue exceeded all my expectations. Here&#8217;s the timeline:
</p>

  1. <div align="justify">
      A lot of time was spent reviewing the many Plug-Ins that my site uses or even In-Active ones. I had to decide what to remove forever, and for others I was making sure there isn&#8217;t a newer version available that should minimize my chances of incompatibilities.
    </div>

  2. <div align="justify">
      Upload of new WordPress.org PHP and related files, was rather painless. Don&#8217;t forget to review additions to wp-config.php in root directory, it needs to be kept, but it has to have additions, and 2.6 had 3 more parameters than my older config.
    </div>

  3. Upgrade of DB itself was easy, don&#8217;t forget to backup database before the move!
  4. <div align="justify">
      I quickly found that my Categories got all messed up. In-fact they were there, but without any names. I think it is a result of my having one category with single quote in it (O&#8217;Rly). At first I picked up database backup, found what used to be in wp-category table and applied the category names onto records.
    </div>

  5. <div align="justify">
      But that was only half the story, since I used Simple Tags plug-in in the past, I was trying to figure out how to move from those old Tags into the new world. Well, apparently there is a nifty embedded tags importer, thanks to <a href="http://wordpress.org/extend/plugins/simple-tags/faq/" target="_blank">simple tip in FAQ</a>.
    </div>

  6. <div align="justify">
      Once All Tags from old posts were imported/converted and such, I setup a Tag cloud Widget on my sidebar, and made minor change to my Theme to show Tags under posts, instead of Categories.
    </div>

<p align="justify">
  At this point I was sure that Upgrade is done, and I decided to celebrate the success by posting something. Funny thing, the Draft uploaded just fine through my Windows Live Writer, which I often use, but the final Post didn&#8217;t want to go up. Kept failing.
</p>

<p align="justify">
  Took me a couple of back and forth to realize that the difference isn&#8217;t "Draft&#8217; to "Publish", the difference is the fact that I added image, as I often do towards the end of post creation.
</p>

<p align="justify">
  Well, long story short, many hours of investigation, logs review, forums checking, later, it looks like there is a freshly minted WordPress bug. Seems that whatever fancy technology generates Thumbnails for uploaded images, is hard-wired to default to /wp-content/uploads directory. Granted that many blogs have their images there, but mine are elsewhere!!
</p>

<p align="justify">
  Hopefully this is just a small thing that <a href="http://ma.tt/">Matt</a> and Co can work out quickly. So just wait until inevitable 2.6.1 version, like I should have&#8230;
</p>

<p align="justify">
  Meanwhile, I decided to spice things up just a little bit to celebrate the Upgrade. Presenting <a href="http://www.adir1.com/chat/" target="_blank">Virtual Chat Room</a>, where you can interact with me and/or other visitors of this blog. I know I am not much of an interior decorator, but I will try to improve in the future! Meanwhile, visit the new <a href="http://www.adir1.com/chat/" target="_blank">Chat page</a> and Suggestions Welcome!
</p>

<p align="justify">
  <strong>PS</strong>: Note how there are no images on this post ;-)&#160; Nor can I figure out how to add Tags from Live Writer&#8230; As my daughter brilliantly noted: "I thought Upgrade was supposed to improve things, not break them!"
</p>

<p align="justify">
  <strong>UPDATE:</strong> I can not explain it, but today I changed my upload directory back to just say uploads, and it works fine, at least from Online uploader. Perhaps I did something wrong on Sunday, but first, I shall try the live writer next, to confirm that it uploads from there!
</p>