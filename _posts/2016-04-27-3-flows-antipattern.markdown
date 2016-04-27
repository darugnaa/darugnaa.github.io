---
layout: post
title:  "3 flows antipattern"
date:   2016-04-27 18:32:00
tags: coding
categories: coding, english
---
While maintaining an old Java enterprise application I got lost in the classical spaghetti code you would expect. After some days of staring at weird walls of code, huge classes and methods with *at least* one side-effect, I finally understood the logical flow of the program.

It isn't easy to explain what each method does and how it achieves the result. This confusion arises from the fact that many classes violate the [single responsibility principle](https://en.wikipedia.org/wiki/Single_responsibility_principle) in the same way: by having exactly three responsibilities. I call each one of these responsibilities "code flow".  
The first code flow is the regular one, when the application functions as expected. The second code flow is the error handling flow: whan something goes wrong take the `else` branch. The third code flow is the test flow, when some flag is enabled return predefined data or do not call external services.

I named this situation "3 flows [antipattern](https://en.wikipedia.org/wiki/Anti-pattern)". A clean design of code separates the three flows into multiple classes (each one having exactly a single flow) using the most appropriate language features (interfaces, exceptions).

More on code design topic coming soon in a longer post.
