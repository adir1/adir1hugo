---
title: WordPress Security Breach – First Response Steps
author: Adi R
type: post
date: 2009-09-06T07:17:29+00:00
url: /2009/09/wordpress-security-breach-first-response-steps/
tags:
  - Scobleizer
  - Technology
  - WordPress

---
<p style="text-align: justify;">
  Word gets around on Internet quickly, but apparently not quickly enough for me. I do recall noticing somewhere a word about small security breach in WordPress 2.8.2 few days ago, but it wasn&#8217;t clear to me that <span style="color: #ff0000;"><strong>all earlier WordPress versions</strong></span> were affected, so I did not rush and act right away.
</p>

[<img class="size-full wp-image-452 alignright" title="Wordpress Logo and Stats" src="/uploads/2009/09/Wordpress-Logo-and-Stats.png?resize=244%2C251" alt="Wordpress Logo and Stats" width="244" height="251" data-recalc-dims="1" />][1]

<p style="text-align: justify;">
  Big mistake, after reading today what happened to <a href="http://scobleizer.com/2009/09/05/i-dont-feel-safe-with-wordpress-hackers-broke-in-and-took-things/">Scobleizer</a> (top of <a href="http://www.techmeme.com/">Techmeme</a>, so thanks to both for heads up), I rushed to make the most recent backup of my blog and upgrade it to 2.8.4 wordpress. The upgrade itself was quick and painless (as usual with wordpress), and it actually much improved, as auto upgrade of plugins worked flawlessly in this latest edition (haven&#8217;t tried full upgrade yet).
</p>

<p style="text-align: justify;">
  I thought I was out of the woods, but reading people&#8217;s comments, they mentioned an Admin account, that hackers create for themselves. Not seeing anything in the Users list, I was not worried at first. But then, someone mentioned &#8220;hidden&#8221; in their comments. So I went to WordPress tables in mySQL and FOUND A HIDDEN ADMIN account created there! Complete, with evidence of crime! The darn trick is as simple as inserting malicious JavaScript which elevated the user to Admin, into their own First Name field!!! I promptly deleted the invader&#8217;s account, and hopefully this is the end of that (read below about other things I checked).
</p>

<p style="text-align: justify;">
  I must say I am disappointed with WordPress security, although it remains the easiest to use and very fast/flexible framework for blog/site. But, haven&#8217;t we learned from all SQL injections in the past? Validate Field Lenghts on the Server Side!!! Especially for any input/fields or account registrations that are in World Visible unsecure area!
</p>

<p style="text-align: justify;">
  I know the hack was fixed in 2.8.4, and I haven&#8217;t taken the time to review how it was fixed. But, I truly hope this is something they go back and double check elsewhere, as much as possible.
</p>

<p style="text-align: justify;">
  I don&#8217;t know if this breach left any other backdoors on my blog, I certainly hope not. Here are some steps I took to review site integrity after following standard <a href="http://codex.wordpress.org/Upgrading_WordPress">WordPress Upgrade instructions</a>:
</p>

  * If you do find phantom Admin user in your wp\_users table that you don&#8217;t recognize, check if that user has wp\_user\_level of 10 in the wp\_usermeta table (same user\_id) &#8211; Record the offending user\_id or IDs (if you have multiple breaches). Promptly remove all records from both tables for that user_id, obviously.
  * Review all other tables, especially wp\_posts, for found user\_id above (called post\_author in the wp\_posts table). It also helps to review any old posts and check their post_modified field, to check for any recent modifications that you didn&#8217;t perform yourself.
  * Review your file system for any new files. I presume that you upgrade as per instructions and completely wipe your old wp-admin and wp-include directories before placing new ones there. But, what about wp-content with your Theme, plugins, widgets and uploads? Review these directories as much as possible!
  * I have no idea how to review wp_options table and whether anything suspicious may be lurking there &#8211; If you have suggestions on this one, post in Comments!

<p style="text-align: justify;">
  Here are some more links to review from <a href="http://wordpress.org/development/2009/09/keep-wordpress-secure/">experts</a> and fortify your site as much as possible. Of course, you may also reconsider moving into relative safety and simplicity of hosted blog, such as WordPress.com and others.
</p>

<p style="text-align: justify;">
  Me, I prefer the &#8220;fun&#8221; of messing with my own site, and having complete control, <strong>seemingly</strong>.
</p>

<p style="text-align: justify;">
  <strong>UPDATE</strong>: Found another <a href="http://ocaoimh.ie/did-your-wordpress-site-get-hacked/">older post</a>, but more good suggestions there. For example, I did review my .htaccess file and found it a bit suspicious, so I replaced it. I just forgot to explicitly mention it above. Better stay alert!
</p>

<p style="text-align: justify;">
  <strong>UPDATE2</strong>: I am still lurking around the Net and reading up on this. Seems that latest vulnerability could also allow someone to reset Admin password of the &#8220;default&#8221; initial WordPress account. So, I also took the precaution of resetting that password to something new ASAP. Read up more <a href="http://wordpress.org/development/2009/08/2-8-4-security-release/">here</a>.
</p>

 [1]: http://wordpress.com