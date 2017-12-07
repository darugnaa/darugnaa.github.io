---
layout: post
title: "Load a resource into a String in Java"
date: 2016-09-13 20:20:00
tags: coding, java
categories: coding
---
Recently I needed a simple method to load a file from resources into a String. Even if it looks like a very simple task, it usually involves many awkward transformations and exceptions catching.  
This solution uses a [Scanner](https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html)
to read the entire `InputStream` into a `String` object.

	private String loadFromResources(String resourcePath) throws Exception {
	    try (InputStream is = getClass()
	            .getClassLoader().getResourceAsStream(resourcePath)) {
	        Scanner sc = new Scanner(is);
	        sc.useDelimiter("\\A");
	        return sc.next();
	    }
	}

The code takes advantage of Java7 [AutoCloseable](https://docs.oracle.com/javase/7/docs/api/java/lang/AutoCloseable.html)
interface and [try-with-resources](https://docs.oracle.com/javase/tutorial/essential/exceptions/tryResourceClose.html)
statement to reduce boilerplate code. In case of exceptions the underlying input stream is closed automatically.

It works by setting `\A` as a delimiter. This regexp [Pattern](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html)
looks for the "beginning of the input" token which of course can't be reached
and causes all the input to be picked up by `next()`.  
Using the actual class' classloader works very well in OSGi environments too (e.g. Apache Karaf, JBoss Fuse).
