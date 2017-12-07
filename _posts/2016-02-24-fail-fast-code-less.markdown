---
layout: post
title: "Fail fast, code less"
date: 2016-02-24 19:49:00
tags: coding
categories: coding
---
I'm embracing the "fail fast" philosophy in every project I can. What is it exactly?
It is about gracefully failing when something goes wrong, and do it as soon as possible.
A suggested and more in-depth article is the [original "fail fast" (pdf)](http://martinfowler.com/ieeeSoftware/failFast.pdf)
by Martin Fowler.  

I have discovered that this approach works really well in modern Agile development, as
it helps in reducing bugs and improves robustness. This sounds good but
how to do it in practice? I would like to share my experience with you.


### Configuration
Most applications need configuration, from a file or other sources. Often it
gets complicated, long, and may be in a format prone to errors (ini files, java
.properties). Environment variables can get messy too: you add one in the
software and forget to set it in the CI server.

Then defaults come into play. Default number of threads for a thread pool
may be a good idea. And then you are tempted to add more default values,
for example for date intervals, paths, and so on. I say **defaults, when
used, must be explicitly stated in the logs**.  
The problem with defaults is when the rules to decide them are arcane or complex,
or a default value does not exist (API keys are a good example). The application
cannot work correctly, so it's best to **stop when a configuration property
is invalid or missing**. 


### Log with *Five Ws* in mind
Every configuration issue must be logged before stopping. This holds true for
other issues as well. Logging is not as easy as it seems, I encountered many
unhelpful lines like `An error occurred`. When writing a log statement it is
important to remember the [five Ws principle](https://en.wikipedia.org/wiki/Five_Ws).

- **Who**: stacktraces identify the source of the problem, don't print them but always
add the exception as a parameter in the log statement
- **What**: add details about arguments and/or variables being processed and a
meaningful description of the operation
- **Where**: usually the log library provides class, method and row number
- **When**: log staements grab the timestamp automatically
- **Why**: discovering this is our job

A well written log line will save you lots of time debugging. Remember:  
Bad: `Configuration error.`  
Good: `Configuration error in config.xml, property 'numThreads' must be an integer,
value '45t' not allowed.`


### Global error handler
Wrap units of execution in `try-catch` block (or the equivalent in your language
of choice). For example web requests or background threads should be wrapped.
First, you are free to throw exceptions without the fear of wreaking havoc on
the rest of the application. Second, you log the exception. This helps a lot
when using third party libraries. Not every library correctly log unhandled
exceptions, or they may get logged on another file or stream and pass unnoticed.


### What's the price?
The real price to pay for the ability to "fail fast" is not the time it takes
to write log statemens or exception handling, as it may seem.
The real price is gathering requirements. It's hard to decide what to do in
less trivial situations. Analyzing situations can be time consuming, client's
responses may not be immediate. Such small decisions may have a huge impact on
the rest of your project. I think that having a rock-solid running software
with a validated configuration will save lot of headaches and time in the long
run.  

I hope these suggestions will provide helpful.

