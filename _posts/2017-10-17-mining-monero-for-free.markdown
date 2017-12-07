---
layout: post
title: "Mining Monero for free"
date: 2017-10-17 21:18:00
tags: mining, monero, cryptocurrencies
categories: tutorial
---
[Monero](https://getmonero.org/) is cryptocurrency which uses a
[Proof-of-Work](https://en.wikipedia.org/wiki/Proof-of-work_system) algorithm
that runs on regular CPUs and GPUs. Proof-of-Work, in layman terms, means that
there must be miners who "mine" each block, and get rewarded when they solve a
particular "equation".

Mining is a profitable activity, but you must pay your electricity bills...
unless someone else offers you free CPU cycles! In this article I will show
how to mine Monero for free.  
But who and why is offering free computing power? There are some competitors
in the market who want to hook developers in. Once you start with and know a
platform, you will probably stay there for future projects.  
In the meantime, let's try the platforms!<br />

### Azure
There's a [Free plan](https://azure.microsoft.com/en-us/free/) with Microsoft
Azure, they offer 200$ / 170€ to try their service. It is about 1 month of a
2 vCPU Windows server, or 2 weeks of a 4 vCPU Windows server.  
Just install a miner and start free mining!

### AWS
The [Free tier](https://aws.amazon.com/free/) of Amazon AWS offers 1 year of
a 1 vCPU Windows server. Unfortunately it's throttled, so for most of the
time it won't mine. There's a workaround though: write a script that launches
the miner, checks the hashrate every some minutes and if it's too low, kills
it and waits a couple of hours for the CPU to get back to full speed.

### Which miner?
The fastest CPU miner I know of is [xmr-stak-cpu](https://github.com/fireice-uk/xmr-stak-cpu).
Follow the intructions to enable Large Page Support, it boosts performance
a lot.  
I sent a pull request to enable stdout flushing, so it's possible to read its
status even when running in background through a pipe. To have the miner
report its hashrate set the following two options in **config.txt**:

	"verbose_level" : 4
	"h_print_time" : 120

If you know other platforms that offer some kind of free trial of their cloud
computing, let me know ;-)

If you liked the idea and feel like tipping here's my address ;-)  
`49WuxuU83x7ERhTU5fAvhhJKpsCaSujpLD4EQgS2jYedduimvSnRS7TPieiKvpHNhuLxEoD5Kq18oGGBWjdss1yJPsHhv1q`
