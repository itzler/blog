---
layout: post
title:  "On protocol tokens & on-chain cash flows"
date:   2020-08-11 01:47:15 -0400
categories: jekyll update
permalink: /on-protocol-tokens-&-onchain-cash-flows/
---
_This paper aims to lay out a framework for protocol-generated value flows, the sets of stakeholders to which value is distributed, and how a native token fits in._

<br />
![_config.yml]({{ site.baseurl }}/images/blind.png)
<figcaption align=center>Trying to reason about the makeup of protocol tokens.</figcaption>
<br />

# **Intro**

Protocol tokens might be the most defining facet of crypto’s first 12 years, but there remains a large amount of confusion surrounding their fundamental makeup.

I expect that the vast majority protocol tokens will be **productive assets.** This simply means that like bonds, businesses, farms, etc, protocol tokens grant claim on a stream of cash flow as yield. 

Protocol cash flows are still relatively small, but the **intrinsic value** of a productive asset is the sum of _all future cash_ that it can generate, discounted to the present. These are early stage technology projects , so  if successful, the lion share of cash generation ability lives in the future. 

However, we can’t simply analyze protocol tokens in the same lense as traditional forms of productive capital. For one, protocols distribute cash flows directly to varying sets of market participants, as well as redistribute share of future cash flows between these participants.

Tokens can also grant access to distinct forms of non-cash flow-related utility, and can even be socially accepted as commodity money! Sometimes these additional demand pressures are quantifiable (i.e. a discount token), but often, we can only reason about them qualitatively. How much is governance over a widely integrated DeFi protocol worth to second layer projects, or during a fork choice? 

In combination, tokens have intrinsic value as claim - or potential claim - on future cash flows, as well as a structural demand premium due to granted utility, monetary properties, or positioning in the stack. 

In order to gain better understanding of protocol tokens as a novel form of capital, it’s worth examining the piece that is quantifiably valuable: cash flows. 

# **On-chain cash flows**

A simple way for thinking about how value flows through protocols is as a three-tier model.

<br>
![_config.yml]({{ site.baseurl }}/images/uniswap.png)
<figcaption align=center>Uniswap 3-tier Value Flow (Log Chart) </figcaption>
<br />

**Tier 1:** Protocols facilitate some amount of _total notional volume._ 

For layer-1’s such as Bitcoin or Ethereum, this is total value transacted. For DEX’s, this is exchange volume. For lending protocols, this is total outstanding borrows. It’s simply a measure of the total dollar value of demand for a given service.

**Tier 2:** Protocols capture some portion of total facilitated volume as a revenue stream by charging a cost on users, which I’ll refer to as _protocol revenue_. 

The way in which this revenue stream is generated largely depends on the structure of the given market, as well as the fee structure of a given protocol. With lending markets, compounding interest revenue is generated as a function of total borrows outstanding and prevailing interest rates, independent of borrow turnover. Uniswap’s 0.3% protocol fee is proportional to exchange volume, while 0x generates fees as a function of trade frequency & ethereum gas price, largely independent of volume.

This potential disjointedness between total volume and fee charged revenue is why we can’t rely solely on protocol revenue as a means to see the full picture. A DEX could be doing $100M in monthly volume, but charging no trading fees on its users - clearly its potential to generate cash flow into the future is larger than 0. 

<br />
![_config.yml]({{ site.baseurl }}/images/maker.png)
<figcaption align=center> Maker’s recent protocol revenue is low due to 0% stability fees being set for most collateral types, but *potential* cash flow from $420M in orginated debt is high. </figcaption>
<br />

**Tier 3:** Protocols divvy up the total revenue stream and direct it to various participant groups within the market. 

Protocols are often described as similar to cooperatives in that revenue share is allocated directly to market participants, rather than to a single margin-maximizing entity. This is why there is no easy way to define a blanket “earnings” metric -- protocol stakeholders are far more diverse than shareholders of a business.

# **Protocol revenue distribution**

It makes sense to classify four comprehensive sets of participants to which protocol revenue is distributed:

*   Arbitrary supply-side participants (LP’s, lenders, miners, keepers/liquidators)
*   Arbitrary demand-side participants (DSR depositors, Nexus Mutual claimers)
*   Token-owning supply-side participants (PoS validators, 0x market makers, Keep signers)
*   Token owners 

A protocol token is a productive asset if revenue share is distributed to either of the last two categories of participant. Namely, the token itself, or the token in combination with some service provision, grants claim on a stream of future cash flow. 

It’s common today to see protocols distributing 100% of revenue to ‘arbitrary’ supply-side participants, where a native token is not required to provide the service, nor is revenue share distributed as a function of native tokens owned/staked by the service provider. Within DeFi protocols, this service is usually some form of liquidity provision. LP’s in both Balancer and Uniswap V2 (with no 0.05% protocol charge switched on) are distributed the entirety of protocol revenue.

Most PoW chains have a similar dynamic where all fee revenue is distributed to a non-token-owning supply-side: miners. Bitcoin miners can be thought of as “staking” coupons for future BTC in the form of mining hardware. This is why BTC would not be classified as a productive asset; the mining hardware, rather than the token itself, provides the claim on 100% of protocol revenue.

<br />
![_config.yml]({{ site.baseurl }}/images/dist.png)
<figcaption align=center> Trailing 6-Month (Feb-Aug) Revenue & Distribution by Protocol</figcaption>
<br />

With regards to tokens that are productive assets, the most common model is paying out some share of protocol revenue to token owners as a dividend. Buy & burn mechanisms, like stock buybacks, are simply as if you received a dividend and used it to buy more shares. When tokens are burned with protocol revenue, the effective dividend is paid out to the entire base of token owners. 

Staking rewards - specifically, the share made up by protocol revenue rather than a subsidy - are another form of dividend. Unlike buy & burn models, the dividend is only paid out to token owning participants that are additionally providing a supply-side service: locking capital by staking the native asset. The implied yield on capital receiving a buy & burn dividend is `protocol revenue paid out / total supply * price`, but with staking rewards, the calculation shifts to `protocol revenue paid out /`**`staked supply`**`* price`.

Protocols also tend to vary size of revenue distribution with the _level_ of work provided by a given class of participant. 0x distributes protocol revenue to market makers (weighted by maker orders filled and pro rata share of tokens staked), of which, a sub-portion is paid out to token owners delegating stake to a given market maker. 

# **Dynamic redistribution of future cash flows**

The not-yet-existent Eth 2 economics can help illustrate a case where both varieties of dividend exist in parallel. It’s important to note that subsidies such as block rewards are not productive cash flow, rather, they represent dilution of future cash flows from existing holders to the subsidy recipient. 

<br />
![_config.yml]({{ site.baseurl }}/images/eth2.png)
<figcaption align=center>Eth2 Cash Flow Distribution</figcaption>
<br />

Assuming that either EIP-1559 and/or ETH2 is successfully implemented, Ether would shift in makeup to a productive asset. This more broadly applies to all native assets of PoS chains. Both validators, and stakers delegating to validators, are members of the above participant set where token-ownership is required in order to perform a supply-side service. 

The fee revenue portion of the staking reward (‘tips’) is a paid as a dividend, where delegating stakers will likely receive slightly less share than validators due to the presence of delegation fees. Ether burned as `BASEFEE` in EIP-1559 is another form of dividend, except it is paid out to all token owners. Validators and delegating stakers effectively “stack” both of these forms of dividend, receiving:

- a) the burned fee revenue, where yield on capital is proportional to percentage ownership of the total token supply
- b) the fee revenue rewarded to stakers, where yield on capital is proportional to percentage ownership of total tokens _staked_ 

Considering these protocol revenue distribution dynamics in combination, we see something extremely interesting: **distribution of future cash flows is computationally rebalanced between participant classes in order of their importance to the protocol!** [1]

1. Validators
2. Delegating stakers
3. Token owners

# **Problems with dividend models**

There’s a couple problems with deterministically paying out protocol revenue as a dividend to token owners or token-owning supply-side participants. Buffet explains the first one, which applies to buy & burn models:

_"Repurchases are sensible for a company when its shares sell at a meaningful discount to conservatively calculated intrinsic value … But never forget: In repurchase decisions: price is all important. Value is destroyed when purchases are made above intrinsic value.”_ [2]

Put simply, it makes sense to buy & burn when the asset is cheap and doesn’t when it’s expensive. Using protocol revenue to buyback a token that just pumped 10000% over the last month is probably not the most effective way to allocate surplus cash flow. 

Historically, Maker has been short convexity, diluting owners (MKR flops) when the token is cheap and increasing share of future cash flows (MKR flips) at more expensive levels. 

<br>
<table>
  <tr>
   <td><strong>Burns </strong>(weighted average)
   </td>
   <td><strong>Issuance</strong>
   </td>
  </tr>
  <tr>
   <td>238.5
   </td>
   <td>44.7
   </td>
  </tr>
</table>
<figcaption align=center>MKR Burns vs. Issuance - (Price / Trailing 365-day Protocol Revenue) Ratio </figcaption>

<br />
The other issue with paying out dividends is that you lose out on the natural compounding effect that businesses exhibit in their ability to reinvest retained earnings. 

# **More optimal models**

_“Designed correctly, an effective distribution of a fee stream can further entrench network effects by giving users a direct economic incentive to contribute, generating more defensibility, which in turn, reinforces the viability of the fee stream in the first place.”_ [3]

An optimal token model is one that: 

- a) Incentivizes all sets of protocol participants to perform their given role
- b) Incentivizes all sets of protocol participants to own a single capital instrument as unified upside incentive 
- c) Redistributes ownership of future cash flows to participants in order of importance
- d) Maximizes retained cash flow - either paid out to or claimable by the capital instrument - after accomplishing a, b, and c

As can be seen above in the Eth2 diagram, most protocols have not yet solved sustainable developer funding -- a clearly crucial set of supply-side participants - but iterations on each of the last two points might serve as solutions. 

We see an alternative model with Compound’s Reserves; the protocol retains surplus revenue as a governable, on-chain balance sheet. 

![_config.yml]({{ site.baseurl }}/images/reserves-docs.png)
<br>
<br />
![_config.yml]({{ site.baseurl }}/images/reserves.png)
<figcaption align=center>Compound Reserves USD By Asset, post COMP subsidy</figcaption>
<br />

Reserves can be continuously lent out, improving the interest accrued by true lenders. This grows Compound’s moat, propagating the feedback loop forward, ultimately resulting in more funds accrued as reserves. Through governance, COMP already grants an effective claim over reserves, so the question becomes: **why pay out dividends when you can let retained cash flow accrue to an on-chain balance sheet and continue to compound?**

Reserves are first and foremost used as an intra-protocol insurance cushion, but they could in theory be used for other things. Some safety margin could be determined by governance in order to skim off excess reserves and auction them for COMP as a buy & burn dividend when the price is favorably low. But reserves could also function as a protocol treasury that is computationally rebalanced in order of importance to active contributors, voters, and delegators! 

# **Dilution as funding & cash flow expansion**

Protocols need to incentivize broader protocol goods, which includes things like development, governing roles, and insurance. Allocation to these needs could very well contribute to a better return on capital over the long term vs. paying dividends. 

This can be done using distribution of present cash flows or allocation from a retained protocol treasury, but it can also be done through dilution of future cash flows as issuance. 

MKR issuance through flop auctions is a model where dilution is used as an effectively limitless insurance backstop [4]. Tezos style issuance that rewards contributors of protocol upgrades is another potential use of dilution as funding - I could imagine Compound governors adding something similar if they thought it beneficial. 

Liquidity mining uses dilution as a means of subsidizing an increase in supply-side liquidity, and ultimately demand-side volume (back to 3-tiered structure). Liquidity mining works dramatically over the short term to stimulate demand-side metrics, but the jury is out on how sticky it will be. 

<br>
![_config.yml]({{ site.baseurl }}/images/compound-rev.png)
<figcaption align=center>Compound Daily Protocol Revenue by Asset, post COMP subsidy</figcaption>
<br />

Liquidity mining as a growth strategy also reminds me of the story of Henry Singleton, CEO of Teledyne in the 60’s and 70’s. Over 8 years while Teledyne was trading at high multiples, he bought 130 companies -- all but 2 acquisitions were made using his own stock. These were the returns during the period [5].

<br>
![_config.yml]({{ site.baseurl }}/images/singleton.png)
<figcaption align=center>Singleton returns during issuance spree</figcaption>
<br />

Then, Singleton abruptly changed directions. For the next 12 years, he bought back over 90% of outstanding stock at cheap multiples. Similarly to expanding sales through acquisitions, liquidity mining uses dilution to purchase demand-side volume. Over the long term, protocols can bring future growth into the present through subsidy issuance and then ultimately capture some portion of that expanded value flow. 

# **Thoughts on present & future**

The crypto market has seemed to revert to its unfortunately natural state as a Keynesian Meme Contest, so its either the best time or the worst time to discuss the fundamentals. A few of the recent dynamics can be described through the lens of cash flows.

A lot of a bull market/mania can only be attributed to speculative premium, but cash flows have historically increased by orders of magnitude during these periods. Last cycle, it was fee revenue on Bitcoin and Ethereum and the evidence is clear that this will repeat, but we are also seeing massive expansions in DEX volume, lending volume, etc. 

It’s worthwhile to be wary of forward looking “P/E” ratios, at least if you’re looking for a useful signal. Depending on the trailing timeline, Ethereum’s `Price / Forward-Looking Fee Revenue` ratio has historically _bottomed out_ when it was most expensive. `Price / Trailing 365-day Fee Revenue` tends to serve as a more reasonable signal of cheapness, particularly when price is low as compared to the fee revenues of the previous bull market.

<br>
![_config.yml]({{ site.baseurl }}/images/ethereum-pr.png)
<figcaption align=center>Ethereum Price / Fee Revenue Ratio - Trailing 365-day (Log Chart)</figcaption>
<br />

In addition, we’ve seen dilution of a productive (or non-productive) asset as growth funding in liquidity mining. Subsidies happen to massively outcompete all other yields when assets are trading at large speculative premiums from day 0, and as we know, liquidity mining _can_ produce in large increase in demand-side metrics (possibly legit, possibly not). 

We also have seen a real-time “collateral premium” reflected in assets, due to both low liquidity and demand to chase these yields. Examples include BAT with compound, all YAM farmable assets, etc. This is further proof that tokens very much dissimilar from traditional forms of capital like equity. In addition to their value as productive assets, tokens can exhibit temporary or permanent demand premiums, one of which collateral-dependent yields in farming. 


<br />

_Thank you to Ash Egan, Teo Leibowtiz, and Dan Elitzer for feedback on previous versions_

<br />

# Sources: 

[1] [https://twitter.com/_charlienoyes/status/1041196651283509248](https://twitter.com/_charlienoyes/status/1041196651283509248)

[2] [Buybackquotes](http://mastersinvest.com/buybackquotes)

[3] [Crypto's Business Model is Familiar. What Isn't is Who Benefits](https://jessewalden.com/cryptos-business-model-is-familiar-what-isnt-is-who-benefits-2/)

[4] [https://twitter.com/tomhschmidt/status/1280309859657715713](https://twitter.com/tomhschmidt/status/1280309859657715713)

[5] [The Outsiders: Eight Unconventional CEOs and Their Radically Rational Blueprint for Success](https://www.amazon.com/Outsiders-Unconventional-Radically-Rational-Blueprint/dp/1422162672)


