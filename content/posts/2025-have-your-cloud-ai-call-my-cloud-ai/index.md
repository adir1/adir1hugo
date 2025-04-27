---
title: Have Your Cloud AI Call My Cloud AI - Exploration Of Eventual Consistency
description: I decided to add a bit to the growing corpus of thoughts on isolation, consistency, CRDTS, paxos, repeatable-reads and more. When really all we need is Oneness (and Love)!
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: true
date: 2025-01-31T11:11:11+00:00
url: /2025/have-your-cloud-ai-call-my-cloud-ai/
tags:
  - Cloud
  - Hyperscalers
  - CAP
  - CDN
  - DynamoDB
  - Redis
  - AI

---

## Overview

Much has already been written about [CAP theorem](https://en.wikipedia.org/wiki/CAP_theorem), [ACID](https://en.wikipedia.org/wiki/ACID), Eventual Consistency and more. As we continue to redefine what it means to have "Internet Scale" solution, I thought it would be interesting to take us "back to basics" of what is it we are struggling with in the first place.

## Back To Basics - Buying a PS6

A common example that I trust most people are comfortable with is Shopping Cart. There are multiple consistency and concurrency issues here, starting with tracking your shopping cart content to order-specific details such as delivery address and payment. In our connected world it is common to start shopping on your mobile device, then decide to complete the order via Desktop PC, or keep hopping back and forth until "pulling the trigger". And what about actual availability of that elusive PS6 - with fast moving inventories, how can you be sure it is Really in stock for you to snag?

I'd like to start with Participants:

- Customer (brain)
- Ordering Device(s)
- Seller (platform)

Most engineers tend to focus on solving the "Backend Problem" - they justly recognize that "seller platform" is in reality a complex interconnected system with myriad of modules with various responsibilities, from DB to (mem)cache, to services layers, and must be kept in sync. Already here I think we need to take a step back and realize that our Customer *Brain* is Also a participant in this distributed synchronization problem: If buyer clicked "Add To Cart" on Mobile and then again on Desktop, is it because they wanted 2 PS6 or because they didn't see if it added to cart after first click?

(Disclaimer: This is just an example - at the time of this writing PS6 has not been announced or released)

## What about Slides or Source Code Files?

What appears to be easier to synchronize, is in fact hiding yet another layer of complexity! Imagine simple example of Presentation being edited by two people, who both see an email asking to "Add this important bullet to your Slide Deck". They both promptly add it, one to slide 5 and another to slide 6. Now the presentation is Perfectly Synchronized without conflicts, except there is a Semantical conflict of Information Redundancy! Similarly source code files are also like this, whether changes occur within the same source or across different classes/modules!

## Jepsen: Call Me Maybe

Probably now is the right time to discuss the P in CAP theorem. One fun way to understand it is via famous [Whisper/Telephone Game](https://en.wikipedia.org/wiki/Telephone_game) - where participants whisper a message to each other along the chain. In actual computing systems the "chain" is hard to establish oftentimes, and worse yet - the messages can simply arrive too late, effectively delivering outdated information on top of the current one!

To stay with a real-world example - what if your phone is muted on the way to pick up your Pho Tom (shrimp), while restaurant is trying to call you whether to substitute with Pho Ga or Pho Bo, as they are out of shrimp!

## The Business of Information Decay

Another popular abstraction is to consider information decay: as participants' information degrades over time, how frequently should they sync or request updates? In a way this ultimately reduces to a business decision, as synchronization incurs real-world costs, including network, compute, and storage resources.

The other extreme end of this is *Value* - stale information can eventually become useless, destroying our initial investment to obtain it.

## Information Overload

Often times software experts assume that their DB guarantees strong consistency and they are fine, but the reality is that we need to worry about information decay at every Layer of architecture, and especially on the UI layer. 

## Git - (De)centralized

As I understand this was the big driver for Git invention, to bundle 






## Local-First, CRDT, Paxos and Beyond


While CRDT (Conflict-Free Replicated Data Type) is one approach popularized by 

##

Arguably how we look at the problem is most essential - 


Still this is something I have seen even experienced software architects struggle with, 




## Further Reading

- [Martin Fowler: Patterns of Distributed Systems](https://martinfowler.com/articles/patterns-of-distributed-systems/)
- [Automerge Conflict Resolution](https://automerge.org/docs/documents/conflicts/)
- [CRDTs](https://crdt.tech)
- [Information Decay Paper](https://dl.acm.org/doi/abs/10.1145/2983323.2983719)
- [Another Information Decay Paper](https://dl.acm.org/doi/10.1145/3340531.3417447)


##### OLD STUFF #### 

## CPU GPU ALU TPU DPU QPU 

Non-General Compute 

https://youtu.be/r5NQecwZs1A?si=zTAQjnrIamQOXuRZ

## Surprise Billing - Ultimate Boss

Undoubtedly everyone has experienced at one time or another the shock of unexpected high bill. This just instantly sours the relationship to the brand, often long term. The situation in corporate world is arguably worse as you also need to explain to your manager(s) what happened, going beyond emotional scarring and into "caused us to miss our financial targets" territory (or even loss of employment?).

Between reserved instances, spot-instances, and bugs in IaC or pipelines - this is a strong and constant possibility. And in cross-cloud environment there can also be major swing in networking charges as files gets replicated as needed for various scenarios.

## Finally Free Lunch?

Free Tier at major Cloud providers is really designed to reel you in, but also very hard to compare. Large cloud providers now have armies of marketing gurus and product gurus who spend their days on how to outshine the competition.

My sense is that AI ultimately operates as our tool, as a sort of "faster assistant" for what human would have most likely done anyhow. In fact all the Quant funds have been revising their AI over the years, albeit sometimes after the trades, as a sort of HITL (Human-In-The-Loop) before the acronym gained popularity! A lot of market looks like self-fulfilling prophecies, especially around Technical Analysis patterns, which I also believe is a result of both human emotion actions and AI trained to recognize it amplify it via built-in expectations.

This topic is huge, so I'll relent for now - below is some further reading, if you are interested. I also promise a post with a deeper dive into algorithmic trading in the future.

Meanwhile, I recommend you Buy and Hold companies you personally like in your day-to-day - arguably the easiest and the best strategy over the long term!



![AI Robots trading on NYSE](multiple_AI_bots_NYSE_trading.png "AI Robots trading with each other on NYSE")

{{< alert "image" >}}
**Images By DALL-E 3 from Microsoft Designer**
{{< /alert >}}
>> Prompt: Generate high resolution image of AI robots trading on New York stock exchange floor, sparks fly everywhere
