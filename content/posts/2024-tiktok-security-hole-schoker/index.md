---
title: TikTok is stealing your emails and I found out why!
description: Information leak on TikTok allows to brute-force attack to discover all registered email accounts - sadly this form of leak is rather common nowadays.
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: false
draft: false
date: 2024-09-07T11:11:11+00:00
url: /2024/tiktok-security-hole-shocker-not/
tags:
  - Security
  - Social Media

---
## TLDR

(Disclaimer: Title written by my 11yo son who insisted it must be a click-bait 😃)
Today we noticed that TikTok website is leaking registered emails. Considering TikTok scale it is likely possible to slowly siphon out all their registered emails in the background over period of time, without them noticing.

## In Practice - Most email accounts likely on dark-web already

Some more details on this common vulnerability - their login API (/send_code) discloses whether email is registered in their system or not. So just brute force generation of random emails could reveal valid emails that otherwise may not have been leaked yet from previous hacks. Sample response:

'''json
{
    "data": {
        "captcha": "",
        "desc_url": "",
        "description": "Account doesn't exist",
        "error_code": 1011
    },
    "message": "error"
}
'''

The sad reality is that most email accounts quickly get found out via all kinds of hacks and leaks, and end up on dark-web for sale mostly to spammers and hackers. Interestingly there was a challenge attempted by TikTok initially - showing puzzles to verify if I am human. However simply cancelling the puzzle few times convinced them somehow not to show it any more.

It is also very possible that there is rate limiter setup in front of the API - however this also offers limited protection as slower rate of requests may not trigger it, and attack by randomizing source IP should also confuse it.  

## Recent related Squarespace hack

So what is the big deal? Indeed this vulnerability is quite common, but it can escalate as in a recent interesting case of domains hijacking (and consequentially stealing cryptocurrency). This happened when Google sold their Domain registration business to Squarespace, [which consequentially let anyone register with someone else's email address without verifying ownership](https://krebsonsecurity.com/2024/07/researchers-weak-security-defaults-enabled-squarespace-domains-hijacks/).

## What are good security practices? (Feedback Welcome)

So let me take quick opportunity to share some tips for good security practices. Most important that can't be said often enough is Use Unique Passwords - I am sure there are still countless people out there using same password on a discussion forum as they do for their bank account. Password managers have become quite robust for this, but I personally still keep my most important passwords in my head.
Everything starts with Email Security - ensure your email is protected by 2-factor auth (via Google or Microsoft Authenticator or similar).

Finally for Developers - I wonder how many of your keep long passphrase on your SSH key? And sadly even that can be [cracked in a matter of hours nowadays](https://www.quora.com/How-hard-is-it-to-bruteforce-the-passphrase-of-an-SSH-key) - so rotate your keys often!

## Some Parting Thoughts

Do work with your family to instill good security practices - it can be a trauma for older people to lose their Facebook friends due to hacker, or worse - suffer financial loses...

Specifically regarding TikTok - I think their App is a particularly addicting time sinkhole and can have negative effects on the psyche. While we don't police Internet use at our home, we often actively discuss it as a family to promote self-reflection and increase awareness on spotting misinformation and [deliberate divisive phobia material](https://www.washingtonpost.com/national-security/2024/09/07/russia-election-covert-disinformation-doj/).

{{< alert "image" >}}
**Image by Crystal Clear XL via Nightcafe**
{{< /alert >}}
>> Prompt: Large network of computer servers interconnected by transparent optical lines with shiny orbs running between them. Servers connections show locks on them and fairies in security guard uniforms flying above. Starry night background.
