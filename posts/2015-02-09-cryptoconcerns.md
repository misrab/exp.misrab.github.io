

# Crypto Concerns

_Posted on February 9th, 2015_


## Introduction

After spending some time thinking about cryptocurrencies, I have developed
some opinions on where things are headed. I could be wrong, and these views will no doubt
evolve over time, but I hope there is some reason in them. Cryptocurrency is fascinating,
and definitely has a role to play in the future; the questions are what role and when.

I'll start by talking about Bitcoin and the Blockchain, and then move on to
the Stellar payment infrastructure in a subsequent post, which I currently find promising. I'll assume basic knowledge of how Bitcoin works. For a quick overview, see my [earlier post](/economics/2015-01-17-bitcoin.html) or related resources.

## Price Volatility

My first major concern is volatility. Take a look at the [CoinDesk](http://www.coindesk.com/price/) index of Bitcoin price in USD over the last year:

![price history](/images/cryptoconcerns/1.png)

It's probably not news to you that Bitcoin's price has been somewhat volatile. It is after
all a novel currency. Two questions arise: is volatility a problem, and will Bitcoin's price stabilise?

If we're hoping for a currency for trade of goods and services, and we assume the value of
US dollars and other traditional currencies is relatively stable for the foreseable future (at least through the transition to digital currencies), volatility _is_ very much a problem. If I buy a can of soda today for the equivalent of USD 1 in Bitcoin, I will be upset tomorrow if it turns out I spent USD 100, or even USD 2 retrospectively.

On to the second question: will the price of Bitcoin, or another cryptocurrency with limited and predictable supply stabilise? To answer this, it's worth conducting a thought
experiment in monetary theory. Suppose we live on an island where everything is traded in
seashells. What's the rough value of a seashell, in terms of something (there are no US dollars to compare to)? The relative price of goods and services will determine their relative value to _each other_, but how much is _one seashell_ worth? In other words, how is the base price of a coconut set. It could be 10 seashells, after which all other products could derive their own price. What stops it from being 5 seashells? One perspective is that, subject to limited distortions like human psychology, politics, employement etc., the absolute level of prices (not relative prices) will be largely determined by the supply of seashells. We have to be very careful when describing the supply however. Is it simply the absolute number of seashells? What's the supply we care about?

In a given time period, on average every seashell is spent a certain number of times. If there are 100 total seashells, and only 50 are spent a year, we'd say the
[velocity of money](http://en.wikipedia.org/wiki/Velocity_of_money) is a half (I'm speaking in very gross terms here, but I think the intuition remains). Therefore, the _nominal_ value of all goods and services in that given period of time is just the total
money supply times the velocity of transactions. **This is what determines the rough price of a coconut, our base for comparison**.

If a Bitcoin were a real currency that could be traded for any good or services, disregarding other currencies its value could be in the millions of current USD. Even if we take into account other currencies (which then take a share of the money supply pie), Bitcoin's theoretical value could be astronomical. _This_ is what so many cryptocurrency speculators are betting on.

![wiki money velocity](/images/cryptoconcerns/2.png)
_Taken from Wikipedia_

If someone could snap their fingers and have Bitcoin jump to this value; if all goods and services (or an agreed upon subset) could be traded for Bitcoin; if people could agree on what market the currency underpins, then there is no reason Bitcoin couldn't reach some equilibrium value. The problem is the path there.

Given a more or less fixed supply, and no clear path to stability, **I have serious doubts as to whether Bitcoin will transition to being a real currency for trade**. Of course, it could find niche applications (i.e. machine-to-machine rapid trading), but vanilla trade is unlikely to be one of them.

## Blockchain Scalability

<em>
**Edit** [_22-03-2015_]: [Gavin Andresen](http://en.wikipedia.org/wiki/Gavin_Andresen),
chief scientist of the [Bitcoin Foundation](http://blog.bitcoinfoundation.org/) has written a great article on a [scalability roadmap](http://blog.bitcoinfoundation.org/a-scalability-roadmap/) that addresses many of the issues mentionned here. There are still challenges to overcome, but it seems time and brainpower are being applied to them.
</em>

Okay, so we've seen that perhaps Bitcoin on its own will not be a ubiquitous means of exchange. That said, the [Blockchain](https://en.bitcoin.it/wiki/Block_chain) _is_ a brilliant innovation. Using computational resources of the network to democratise ledger sychronisation without the need of a central authority is amazing. However, while the problem of double-spending is addressed, a new paradox is created: that of scalability.

The Blockchain limits block size (groups of transactions considered to have happened at the same time) to about 1 megabyte. This [video](https://www.youtube.com/watch?v=cZp7UGgBR0I) explains why: if the block size is too big, then expensive, specialised hardware is required to actually solve blocks. This defies the whole idea of a decentralised system: in effect control is returned to large organisations with sufficient resources. Therein lies the paradox: the block size limits the maximum theoretical [number of transaction](https://en.bitcoin.it/wiki/Maximum_transaction_rate) _accross the network_ to about 10 per second. Compare this to VISA (think credit cards), that processes an average of [2,000 transaction per second](https://en.bitcoin.it/wiki/Scalability).

Other, less fundamental albeit important issues also arise. As time goes by, the size of the Blockchain increases. It currently stands at about 29 gigabytes, making storage on a local client impractical. Thus, many clients are now [thin](https://en.bitcoin.it/wiki/Thin_Client_Security). Instead of truly verifying transactions, they rely on trusted nodes, again obviating the whole idea of decentralised security.

<em>
**Edit** [_11-02-2015_]: while studying the Ethereum crypto system, I came accross
a good explanation of Merkle trees and thin clients ([see page 9 of white paper](https://www.ethereum.org/pdfs/EthereumWhitePaper.pdf)). It seems that a thin client _could_ achieve a high degree of security with a smaller version of the Blockchain, albeit one that still likely grows with time.
</em>

## Conclusion

Perhaps some new innovation will address the limitations mentionned, but for the moment both Bitcoin and the Blockchain have significant flaws (despite their admitted brilliance). A path to price stability for Bitcoin is unclear or implausible, restricting it to niche use cases. As for the Blockchain, it has yet to address the paradox of distributed security and scalability.

I remain optimistic about cryptocurrencies. The promises of decentralisation and digitisation are, amongst others, extremely appealing. Hopefully by being critical of existing issues, and creative in addressing them, we'll find the inevitable path forward.

## Acknowledgements

What I do know thus far was mainly learned from open online sources, for which I am extremely grateful as always. These included but are not limited to the [Bitcoin wiki](https://en.bitcoin.it), videos like [this](https://www.youtube.com/watch?v=l9jOJk30eQs) and [this](https://www.youtube.com/watch?v=cZp7UGgBR0I), and of course the [original paper](https://bitcoin.org/bitcoin.pdf) by Satoshi.

Further thanks are due to my brother and close friends, for listening to me think out loud, and for providing wise feedback.
