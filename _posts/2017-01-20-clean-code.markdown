---
layout: post
title: "Clean Code"
date: 2017-01-20 21:20:00
tags: coding, book-review
categories: coding
---
I just read [Clean Code by Robert Martin](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882),
a very insightful book on software development. I thought about it for a while
and decided to write a little review.

### TL;DR version

The book is an interesting read, even if you already know some of the ideas contained.
Do you professionally develop software? Go read this book immediately!

### Long version

Let's start with a quote I particularly like: "_Programming is a craft more
than it is a science. To write clean code, you must first write dirty code
and then clean it._"  
It may sound obvious, but it isn't. The act of "_cleaning_" requires a
precondition: you must know by experience when the code is dirty and decide
to clean it up. Such experience comes from passion, from hard work and from
lessons learned from master craftsmen. The author tries its best to be one of
them.  
As our experience grows, the meaning of "clean" will change to reflect the
new lessons learned. Let's look at some excerpts.

_Software systems should separate the startup process, when the application objects are constructed and the dependencies are "wired" together, from the runtime logic that takes over after startup. [...] One way to separate construction from use is simply to move all aspects of construction to main, or modules called by main, and to design the rest of the system assuming that all objects have been constructed and wired up appropriately._

We all know some of the usual suspects around: [Spring](https://docs.spring.io/spring/docs/current/spring-framework-reference/html/index.html), [OSGi Blueprint](http://www.ibm.com/developerworks/library/os-osgiblueprint/index.html), [Unity](https://msdn.microsoft.com/en-us/library/dn223671.aspx)... There are many frameworks for [inversion of control](https://en.wikipedia.org/wiki/Inversion_of_control) and [dependency injection](https://en.wikipedia.org/wiki/Dependency_injection) around. What we get from them is the ability to work with dependencies without checking for `NULL`s, all object are created and ready to be used. What if something is missing or not constructed? We are going to [fail fast](2016/02/fail-fast-code-less) of course!  
We need dependency injection even if our applications supports one kind of database or a single remote service. Because we will need at least a second database engine: a mock database engine for testing purpose.

_Test code is just as important as production code. It is not a second-class citizen. It requires thought, design, and care. It must be kept as clean as production code.
Tests are very important becase tests enable change. Tests let you know that you didn't break the expected behaviour. Tests let you know that you didn't break the expected behaviour of tested code, that's why test coverage is important too._

Another quote I like about tests:  Test **F.I.R.S.T.**  
**Fast** - Tests should be fast. They should run quickly.  
**Independent** - Tests should not depend on each other.  
**Repeatable** - Tests should be repeatable in any environment.  
**Self-validating** - The tests should have a boolean output. Either they pass or fail. You should not have to read through a log file  
**Timely** - Unit tests should be written just before the production code that makes them pass.

There's nothing as relaxing as the line of green dots of passing tests. Red ones should be fixed immediately, because we want everything green to feel great. How much time would you want to wait after fixing the code to see everything green again? No more than some seconds, I bet.

Tests should be structured as follows:  
_The BUILD-OPERATE-CHECK pattern is made obvious by the structure of these tests. Each of the tests is clearly split into three parts. The first part builds up the test data, the second part operates on that test data, and the third part checks that the operation yielded the expected results._

Also known as [Arrange Act Assert](http://wiki.c2.com/?ArrangeActAssert)
pattern. Almost any testing framework offers its own way to hook into test
lifecycle to setup and clean any resource or data required. Assertions can
show customized messages when they fail.

_**Open-Closed Principle**: Classes should be open for extension but closed for modification. We want to structure our systems so that we muck with as little as possible when we update them with new or changed features. In an ideal system, we incorporate new features by extending the system, not by making modifications to existing code._

Is there anyone not yet familiar with [Decorator](https://en.wikipedia.org/wiki/Decorator_pattern) and [Adapter](https://en.wikipedia.org/wiki/Adapter_pattern) patterns?

There's a lot more in the book than these concepts. For example, there are
examples of "bad code" and how the author proceeds in refactoring it.
