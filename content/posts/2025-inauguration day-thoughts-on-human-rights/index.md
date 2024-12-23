---
title: Human Rights, Individual Freedoms - an Antithesis to Dictatorship
description: An exploration of how can people hold Individual Freedoms and Human Rights as paramount while also believing that Dictatorship governance is viable or even efficient option
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: false
date: 2025-01-20T11:11:11+00:00
url: /2025/inauguration-day-thoughts-on-human-rights/
tags:
  - Markets
  - Economics
  - Quants
  - AI
  - Derivatives
  - Options

---
## TLDR

I discovered the amazing world of algorithmic trading probably about 10 years ago. I was already enjoying the exploration of market dynamics, their correlation with human psyche, economic cycles, and companies hype/performance. This post is my musings about AI impact on Black Box algo-trading, and even if one perfects their AI to make endless profits - is it ethical? No prior Quant expertise required to participate, but basic stock market understanding is a plus!

## Introduction to Algorithmic Trading and Quants

At its core, the idea of algorithmic trading is pretty straight forward. A computer system is programmed with certain rules and empowered by a human to analyze certain Financial market data and decide which stock to buy or sell, and when. It gets exponentially more complex quickly, though, as most strategies (aka: algorithms/rules) involve [trading Options](https://www.investopedia.com/terms/o/optionscontract.asp) also.

The Math Wizards use statistical analysis of a lot of Past data, to try and predict future behavior of the market. One of the best known and oldest such trading funds is [Renaissance Technologies LLC](https://www.rentec.com/). Founded in 1982 they boast 90 PhDs in Mathematics, Computer Science and related fields. They also mention that: "Our research database grows by more than 40 terabytes a **day**"!

So what do they do with all that data? They try to keep their algorithms a secret, but at the core it is a lot of Machine Learning, Reinforced Learning, Decision Trees and even Deep Neural Nets with [Backpropagation](https://en.wikipedia.org/wiki/Backpropagation). Arguably this is actually one of the Easier use-cases - as you have Very specific goal, Maximize Profits, whereas generalized LLMs often operate in murky opinion-based world (especially now in our [post-truth society](https://en.wikipedia.org/wiki/Post-truth)).

## Dark Pools - What are those?

So where are the promised Dark-Pools you ask? I would argue that is a renegade semi-legal branch of algo-trading. It is utilizing Level-2 quotes data to look at Live market orders and predict the sentiment for specific stock or market overall. The idea is pretty basic - if there are a lot of sell orders, and fewer buy orders - clearly stock is bound to go lower in the short-term, and vice-versa. This is usually only useful for high-speed trading, also known as day-trading, but clearly whoever has the fastest computer (and market connection), should be able to "predict" the short-term price swing and trade fast enough to take advantage of that.

This is where our Dark-Pools come in - Large Institutional Funds also have to buy/sell stocks, but obviously they will disproportionally affect the market due to the Large size of their positions (usually **multi-million** dollars) - so it is a Huge signal of *Sentiment* for a stock or even an entire market. In a way [Dark-Pools emerged exactly to Avoid exposure](https://www.investopedia.com/terms/d/dark-pool.asp) of such large participants, but then our human instinct of [Have The Cake and Eat It](https://en.wikipedia.org/wiki/You_can%27t_have_your_cake_and_eat_it) kicked in!

## Ethics of *Market Liquidity*

So what is the problem? Seems legit and harmless enough?! Of course not - the biggest risk is Herd Mentality amplified Thousandfold by similarly trained Systems/Algorithms. If all the computers recognize the same signals (poor company earnings or poor economic outlook), and rush to Sell (or Buy) - the price impact can quickly escalate to Panic levels, causing even further snowball effect!

While market system implemented *some* [Market circuit-breakers](https://www.investopedia.com/terms/c/circuitbreaker.asp) over the years, the risk is all still there.

So why let machines trade stocks independently at all? Well, besides the fact it is realistically impossible to block, many argue it gives human traders certain liquidity.

My thesis here is that this is a false promise - most of the automated systems have endless amount of rules and safeguards, and often in a situation of real "run-on-market" they step back and refuse to counter-trade also! In other words - if an average Joe decides they don't like "company X" any more and want to sell their shares ASAP, most likely a LOT of other people decided the same thing and automated systems detected this "avalanche" and would decide: let's see how low it goes before considering buying again!

## The young "Flash Crash Trader"

An interesting sidebar is a story of a brilliant young trader in England who noticed how several automated systems react to a particular Limit Order (order visible on the Markets L2 order book, but not yet executed). Many systems interpreted it as a certain Sentiment and were triggered to Buy/Sell ahead of it - while in fact the trader was "bluffing", and kept adjusting or cancelling his order shortly thereafter. [Here is the writeup from BBC](https://www.bbc.com/news/explainers-51265169) about him.

## AI or KISS (Keep it Simple *Silly*)?

So how does our enormous leap forward in AI affect these automated systems? Should we rush to regulate them before all our pensions are demolished by another "[Flash-Crash Trader Wiz Kid](https://www.bbc.com/news/explainers-51265169)"?

My sense is that AI ultimately operates as our tool, as a sort of "faster assistant" for what human would have most likely done anyhow. In fact all the Quant funds have been revising their AI over the years, albeit sometimes after the trades, as a sort of HITL (Human-In-The-Loop) before the acronym gained popularity! A lot of market looks like self-fulfilling prophecies, especially around Technical Analysis patterns, which I also believe is a result of both human emotion actions and AI trained to recognize it amplify it via built-in expectations.

This topic is huge, so I'll relent for now - below is some further reading, if you are interested. I also promise a post with a deeper dive into algorithmic trading in the future. 

Meanwhile, I recommend you Buy and Hold companies you personally like in your day-to-day - arguably the easiest and the best strategy over the long term!

## Some further reading to explore

- [What is Technical Analysis](https://www.investopedia.com/terms/t/technicalanalysis.asp)
- [Quant Funds that beat the stock market](https://medium.com/@siddharth.bhaisora/best-quant-funds-that-beat-the-stock-market-1597ca160df5)
- [A Random Walk Down Wall Street](https://www.amazon.com/Random-Walk-Down-Wall-Street-ebook/dp/B0B3G6FVT5/)

![AI Robots trading on NYSE](multiple_AI_bots_NYSE_trading.png "AI Robots trading with each other on NYSE")

{{< alert "image" >}}
**Images By DALL-E 3 from Microsoft Designer**
{{< /alert >}}
>> Prompt: Generate high resolution image of AI robots trading on New York stock exchange floor, sparks fly everywhere
