# REPLAY
https://www.youtube.com/watch?v=iDxMhUxnXsg

# Q&A
Is competition lower where markets are “thin” and move a lot (prices get “corrected”) even on smaller trades?
Kris Longmore       23:15
Yeah it tends to be... the bigger players generally want to be playing in more liquid markets where they can get more size on, otherwise it tends not to be worth their while. But edges can show up in liquid markets too... it's just that they'll generally have something about them makes them unattractive to the big guys. James will talk about that shortly I think.

how would one manage risk if lets say doing cross CEX arb on corn but dont have access to spot shorting or perp
Kris Longmore       23:27
That's potentially tricky... probably a mix of appropriate sizing, possibly hedging in correlated markets....

Couldn't the supply/demand mismatch between exchanges be due to one exchange having a 'more informed' buyer/seller 'leading' price discovery? would timescale that you choose play a big role in the exchange arb like this?
Kris Longmore       23:29
It could for sure... but you'd still have an arbitrage opportunity. In terms of timescale - in practice with these sorts of trades you're usually going to be constrained by how fast you can react to stale prices.

So it looks like you begin with a hypothesis (e.g., cyclical/seasonal effects of rebalancing should show up at different days of the month) and test via data analysis (e.g., log returns at each day), and that is your napkin-written test for an idea before further exploration/optimization?
Kris Longmore       00:34
Deebz that is exactly it in a nutshell!

In a similar vein, could you use relative markout performance as a proxy for alpha decay?
Kris Longmore       00:37
Mayyyybe.... but you have to be really careful about distinguishing between normal variance and decay.... in practice you don't really know until you've lost some money (unless you're doing something high frequency or trading something structural that you can directly observed has changed)... so you have to manage the possibility that your strategy no longer works through other means - diversification, appropriate sizing.

When do you know when to hedge a strategy like this vs just let the delta's ride?
Kris Longmore       00:39
This very much depends on you and your constraints. In our traidng, we'd almost always let the deltas ride and accept the added variance, because we're more interested in total returns and have a pretty strong stomach for risk. Most people probably wouldn't enjoy this approch though, at least when they're starting out. Very much a personal/constraints-driven thing, rather than something you'd extrapolate from a strategy itself.

What is your source for market and fundamnetal data ?
Kris Longmore       00:40
We use a number of providers... Sharadar for equities, Norgate for futures, Orats for options, Tardis for crypto. Plus we record some of our own.

Do you think trend following and/or momentum have an edge? Would you say it's simply front running other people?
Kris Longmore       00:46
I think it does... in the right market. We were trading a trend and momentum strategy in crypto recently for example. Commodity trend would have done great this year after a long period of going nowhere. And yeah, I think front running other people is a good model of trend following... you're essentially getting in early on the slow diffusion of information....

Is there any good signs that your backtest may be inaccurate? I’ve been backtesting a pairs trading strat on minute data and it’s been getting a sharpe of 3. Obviously this is nonsense but can’t find the bias/error in the backtest. Any advice?
Kris Longmore       00:51
Yeah definitely.... good on you for recognising that that sort of performance is probably a bug. When you backtest on minute data, you get some weird biases - for example, normal bid-ask bounce will make it look like a mean reversion strategy was highly profitable, which I suspect is what's going on with your data. Dealing with that bias isn't trivial, but you can get part of the way there by (1) aggregating to a lower frequency, (2) calculating a TWAP or VWAP over some time period - both approaches should remove at least some of the bias.

What do you guys think about momentum/trend/value short-long strategies in crypto? these strategies worked in tradfi with good sharpe, what do you think about them in crypto? I backtested some, but we don’t have enough data in crypto to be sure
Kris Longmore       00:56
We were recently trading a crypto momentum/trend short-long thing that was pretty good until FTX blew up! So I think there's a basis for doing that in crypto. Not sure about value... obviously valuing crypto is kinda fraught, but if you could come up with a sensible measure, I wouldn't be surprised if you could trade it long-short.

When you look back on a year, how do you measure the success of the trading year?  Obviously total return. But does sharpe ratio matter to you?  If so what’s a reasonable sharpe ratio to aim for?
Kris Longmore       00:59
I kind of measure it by how sane I managed to stay!!! No, in all seriousness, it very much depends on your personal preferences and constraints. We don't really care about sharpe (although of course, a high sharpe is nicer than a low one!!). I'm more interested in total returns. Totally personal/constraints-driven though. In terms of what sharpe is achievable... again depends on what you're doing, but for a portfolio of low-frequency strategies that you can harness as an independent trader, I think Sharpe 1.5 is totally achievable in the long run (individual years will vary)
