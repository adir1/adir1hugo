---
title: Swimming in the Dark Pools. Musings on the Morals of Algo Trading.
description: Quant and Algorithmic trading concepts, black box and ethics, musings on morals and true usefulness of derivatives - not even mentioning Futures markets 
author: Adi Rabinovich
type: post
heroStyle: "background"
showTableOfContents: true
draft: true
date: 2024-08-11T11:11:11+00:00
url: /2024/swimming-in-the-dark-pools-quants-ai-trading/
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

## Dark Pools - What are those?!

So where are the promised Dark-Pools you ask? I would argue that is a renegade semi-legal branch of algo-trading. It is utilizing Level-2 quotes data to look at Live market orders and predict the sentiment for specific stock or market overall. The idea is pretty basic - if there are a lot of sell orders, and fewer buy orders - clearly stock is bound to go lower in the short-term, and vice-versa. This is usually only useful for high-speed trading, also known as day-trading, but clearly whoever has the fastest computer (and market connection), should be able to "predict" the short-term price swing and trade fast enough to take advantage of that.

This is where our Dark-Pools come in - Large Institutional Funds also have to buy/sell stocks, but obviously they will disproportionally affect the market due to the Large size of their positions (usually **multi-million** dollars) - so it is a Huge signal of *Sentiment* for a stock or even an entire market. In a way [Dark-Pools emerged exactly to Avoid exposure](https://www.investopedia.com/terms/d/dark-pool.asp) of such large participants, but then our human instinct of [Have The Cake and Eat It](https://en.wikipedia.org/wiki/You_can%27t_have_your_cake_and_eat_it) kicked in!

## Ethics of *Market Liquidity*

So what is the problem? Seems legit and harmless enough?! Of course not - the biggest risk is Herd Mentality amplified Thousandfold by similarly trained Systems/Algorithms. If all the computers recognize the same signals (poor company earnings or poor economic outlook), and rush to Sell (or Buy) - the price impact can quickly escalate to Panic levels, causing even further snowball effect!

While market system implemented *some* [Market circuit-breakers](https://www.investopedia.com/terms/c/circuitbreaker.asp) over the years, the risk is all still there.

So why let machines trade stocks independently at all? Well, besides the fact it is realistically impossible to block, many argue it gives human traders certain liquidity.

My thesis here is that this is a false promise - most of the automated systems have endless amount of rules and safeguards, and often in a situation of real "run-on-market" they step back and refuse to counter-trade also! In other words - if average Joe decides they don't like "company X" any more and want to sell their shares ASAP, most likely a LOT of other people decided the same thing and automated systems detected this "avalanche" and "thinking": let's see how low it goes before we consider buying again!

## The young "Flash Crash Trader"

An interesting sidebar is a story of a brilliant young trader in England who noticed how several automated systems react to a particular Limit Order (order visible on the Markets L2 order book, but not yet executed). Many systems interpreted it as a certain Sentiment and were triggered to Buy/Sell ahead of it - while in fact the trader was "bluffing", and kept adjusting or cancelling his order shortly thereafter. [Here is the writeup from BBC](https://www.bbc.com/news/explainers-51265169) about him.

## AI or KISS (Keep it Simple _Silly_)?

So how does our enormous leap forward in AI affect these automated systems? Should we rush to regulate them before all our pensions are demolished by another "[Flash-Crash Trader Wiz Kid](https://www.bbc.com/news/explainers-51265169)"?



This topic is huge, technical charting is super popular and not fully automated as far as I know. AI analysis of many sources. More Advanced post is coming - to dive deeper into those issues for those interested.


## Some related links to explore

- [Netflix Shows Cancelled in 2022](https://variety.com/lists/netflix-shows-canceled-2022/)
- [Interview with Netflix new Co-CEOs - a window into their thinking](https://www.bloomberg.com/news/newsletters/2023-01-21/netflix-ceo-reed-hastings-steps-down-interview-with-greg-peters-ted-sarandos)
- [Netflix push into video games](https://www.theverge.com/22772589/netflix-video-games-app-news-updates) - I plan to blog in the future on this Exciting effort
- [How We Decide by Jonah Lehrer](https://www.amazon.com/How-We-Decide-Jonah-Lehrer/dp/0547247990?tag=craftonia-20)
- [Predictably Irrational](https://www.amazon.com/Predictably-Irrational-Revised-Expanded-Decisions/dp/0061353248?tag=craftonia-20) - Expanded edition of the classic

{{< alert "image" >}}
**Images By DALL-E 3 from Microsoft Designer**
{{< /alert >}}
>> Prompt: Generate high resolution image of AI robots trading on New York stock exchange floor, sparks fly everywhere
