---
title: Composability, Virtualization, Efficiency, Security - Can we have it all?
description: An exploration of how our ongoing efforts in software design and runtime design somehow still eons away from optimal
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: false
date: 2025-02-22T11:11:11+00:00
url: /2025/the-next-programming-revolution/
tags:
  - Programming
  - Software Architecture
  - AI
  - Agents
  - Cloud
  - Containers
  - Performance
  - Hyperscalers

---

## Overview (TLDR)

Composability is one of those longest and toughest challenges in software, and it doesn't look to me as we have solved it just yet. Industry move to Virtualization and Containerization brought with it many benefits, but also additional overheads that we must keep in mind and analyze. In this part 1 of the series, I recount where we are and how we got here.

## One Ring To Rule Them All

<img src="Operating_system_placement.svg.png"
     alt="Operating System Layers Diagram"
     style="float: right; display: inline; margin-left: 10px; margin-bottom: 10px" width="30%" height="300"/>
Let us start with the basics. All computers, from large servers to smallest Android phone in your pocket, are running an Operating System. Modern OS does a lot, but my focus today is on execution protection layers.

The CPU has [protection rings](https://en.wikipedia.org/wiki/Protection_ring) - to ensure only OS Kernel and Drivers code have full access to computing resources, while user-space (aka: Apps code) is effectively limited and controlled by the OS. While this arrangement makes a lot of sense, there is immediate overhead in executing Apps when they need to ask OS for "services" - and those arguably happen constantly. Apps need to access network, (many) files, screen and other hardware devices (via drivers) and more! So there is constant overhead for CPU to "switch" between rings, and although it is not as pronounced with Phone Apps, on Servers where every nano-second counts, it is definitely impactful.

## Software Composition

As we rushed to package our Apps for distribution onto Phones and Clouds, one straight forward approach was to use virtual machines. And while virtualization does give us the flexibility to run large variety of software applications, it usually executes slower, and can often require a translation layer to adjust our simulated "machine" to the actual hardware.

The next revolution brought us containers, cheered for many benefits - from consistent dependencies management, to portability, isolation and even some security. Still Linux C-Groups, the leading mechanism for management of container resources during execution, introduces additional complexity and overheads (loading duplicate libraries into memory and more).

Today most developers see themselves as Lego block builders - figuring out which small/big blocks to use where, to ensure they fit in an optimal way. Yet almost as soon as the first version of an "App" is released, few lego blocks become "obsolete" - and it is VERY challenging to replace them without completely breaking the whole construction down or making it into an Ugly (and usually Unlivable) mess...

## Containerized Oil Tanker

One interesting way of looking at the problem is as a large Oil Tanker! Lets say we need to transport oil from one location to another. The fewer large "containers" we use on our ship, the more oil we can fit and the fewer heavy metal walls/containers we will require. However there are some significant downsides - for example in case of a damage to a wall only single container will spill out, rather than entire ship. Or what if we need to move multiple different types of oil?

## Walk the Talk

What I realize is that our journey is more about where we started - with large servers and data centers helping companies organize world's information. Then we realized that there are large benefits in sharing the data-centers between companies, and leaving their operation to the experts. Yet as we move to this public cloud infrastructure (aka: Hyperscaler data-centers), we are still exploring the best organizational approach that balances speed, cost and security.

My sense is that we are yet to figure out the "Optimal" end state, perhaps then we can prepare a more solid strategy of how to get from "here" to "there". Meanwhile I say lets enjoy this exploration of combination-space together!

## Parts 2 and 3 now posted

- [Human Developers Edge over AI](/2025/human-developers-edge-over-ai/)
- [Introducing Merka Cloud](/2025/introducing-merka-cloud/)

## Some further reading to explore

- [Container Runtimes Compared](https://www.wiz.io/academy/container-runtimes)
- [Virtual Machines](https://en.wikipedia.org/wiki/Virtual_machine)
- [Operating Systems](https://en.wikipedia.org/wiki/Operating_system)
- [System on a Chip](https://en.wikipedia.org/wiki/Protection_ring)
- [History of OLE from Microsoft, early componentization attempts](https://en.wikipedia.org/wiki/Object_Linking_and_Embedding)

{{< alert "image" >}}
**Featured image by me via NightCafe - using Flux Schnell model**
{{< /alert >}}
>> Prompt: Large Oil Tanker with some containers on top, with beautiful sunset in the background and few coastal birds in the foreground.
