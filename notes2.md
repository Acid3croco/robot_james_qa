# REPLAY
https://www.youtube.com/watch?v=Nbq5eyVk-0w

# TECHNIQUES
Starts a 45-50min in the video

# Q&A
The idea of finding and exploiting market inefficiencies kinda cuts everyone not intimately familiar with how professional financial industry works, right?
Kris Longmore       10:20
I don't think it cuts everyone like that out necessarily... but certainly understanding how people tend to trade under different constraints can help pose hypotheses about why an effect might exist.

can you consider bad prices on htf or even at let's say, 1-5m candles / nr of ticks ? For candles, I guess the bad price continues from fair to bad the more time it takes to evolve ? something like a divergence but in time
Kris Longmore       10:23
You certainly can go looking, and you'd find that opportunities exist. You tend to find though that effects that play out over short time scales see more competition, at least in liquid assets, making them hard to compete for

I am feeling mildly demotivated as finding such inefficiencies in the market is extremely hard.
Kris Longmore       10:30
Yeah it is... The reality is it's a really hard way to make money. In my experience, the people who succeed in this game tend to love the process, the research, the work. The difficulties are what makes it so exciting.

Why log returns and not just normal returns? What’s the difference?
Kris Longmore       10:32
Mainly because they're easier to aggregate through time

In this example, would it not be fair to assume that price insensitive trading may cause lower time frame exploitable mispricing as opposed to necessarily seeing obvious return distributions such as the one seen in the slide (low at the beginning of the month, high at the end)?
Kris Longmore       10:35
The slide was really a stylised version of the effect... in reality it's not nearly as clean. It play out noisily and on average, and certainly not every month. That slide implied a level of precision that doesn't really exist... but I hope it's helpful in understanding the effect.

do you have any recommendations for people we could nick ideas off?
Kris Longmore       10:36
In the public sphere - Euan Sinclair, Rob Carver

is that bad if we data mining, find anomaly then trying to find the story related to that phenomena?
Kris Longmore       10:37
I wouldn't say it's bad necessarily... and to be honest we do a bit of this ourselves sometimes. Ideally we wouldn't do it this way, but if you know what you're doing, a bit of data mining can be a useful thing.

So other than being in the industry how one would go about learning the market inefficiencies that you discuss (other that learning from rw ofc)?
Kris Longmore       10:39
You've just gotta get your hands dirty... read widely, do your own analysis, talk to people. The last one of those is probably the most productive. And these days, you can talk to people without being "in the industry" on Twitter. In particular, check out some of the people James follows and talks to... they often share really useful stuff.

probably better to use the median than the mean if the distribuition is skewed
Kris Longmore       10:50
Yeah... that's a fair point Ricardo. I would use the mean at this stage of the analysis though, just in order to see if there is an effect at all. Then, when I want to understand that effect in more detail, I might go ahead and look at the skew. We tend to do the simplest thing first and go from there. It's quite a productive approach for the trading application.

kinda off-topic but where can I find some info on James's background. For Kris I could find forum posts, interviews, for James not so much.
Kris Longmore       10:51
I think there's a brief blur on the About page of the RW website. I can give you the abbreviated history... physicist by training, worked in enterprise software development, sales, and consulting before switching over to prop trading.

Probably would be nice to run a t-test as well to confirm the difference in the means we see is statistically significant one (end of month vs beggining of month)
*Answered audio* 10:50 so prly around 50min in video
Yes but some more simple things can be done

let's assume you found a bunch of anomalies to trade. how would you go about position sizing/aggregating them into a portfolio?
Kris Longmore       10:57
That's a BIIIIG question!! I'll try to give a useful but brief answer...
Very much depends on your own constraints and objectives. But here's a good general approach:
1. Start with the assumption that everything gets an equal weight. I like to use the volatility targeting approach, so this means assume that everything gets an equal vol contribution to the portfolio.
2. Look at the returns distribution of the individual strategies. Does anything have a nasty skew or fat tails? (it usually will). If so, knock down it's vol contribution a little.
3. Think about how confident you are in the effect. If less confident, or you have less data, knock it down a little more. If super confident, bump it up a little.
That's kinda a high level framework for thinking about the problem...

Just come to my mind that this could be found from data mining if we have calculated returns by date of month far all assets. We would get lots of false positives, but maybe there would be some pattern after robust analysis.
Kris Longmore       11:03
Yeah... you'd find this effect if you data mined for it. That can get awkward though if you don't have any reason for it to exist.
What you say is true though, and in reality, research tends to be iterative. For instance, you might notice something like this via a data mining exercise, then fit an explanation to it after the fact and iterate from there. That's not as "clean" as the ideal process we've described here, but it's probably more reflective of reality. Good comment, thanks Mislav.

could be good for each day to create a return distribuition by bootstrapping, then will be easy to create confidence intervals for the mean daily return
Kris Longmore       11:03
Yeah... that might be something you'd do later in the process... it would be just one more bit of evidence you could add to what you've found so far.

How would one best pick the subperiod length such that it is in sync with and adequately captures the periodicity of the recurrent effect we're trying to confirm / reject? Go with heuristics or is there a more systematic approach?
Kris Longmore       11:07
Good question... it's probably less precise than you're imagining though. Basically finger in the air splitting the data into several periods that have a reasonable amount of data. No hard and fast rules though. And ideally would be fairly consistent to different approaches to splitting.

Is this process also a good starting point for more hft things, or is something really different when going much faster (latency wise) ?
Kris Longmore       11:14
Yeah it is... although for HFT things you'll find that things are generally more clear cut. In that game, you're doing things like hitting stale quotes... which doesn't require a ton of this sort of data analysis. Instead, you'd be more interested in analysing how fast you need to be to capture the effect, understanding your own latencies etc.

How many strategies like this would you be running simultaeneously?
Kris Longmore       11:21
Great question... in an ideal world, as many as possible. Honestly, once you start doing this a lot, you'll have more to trade than you can manage comfortably. It becomes an operational constraint... which is very real, given that many independent traders have a job and other stuff going on their lives.

You omitted the most important part, check the data. Esp from free source they may be crappy.
Kris Longmore       11:34
Yep great point!!! Many a perceieved inefficiency has turned out to be simply bad data!
