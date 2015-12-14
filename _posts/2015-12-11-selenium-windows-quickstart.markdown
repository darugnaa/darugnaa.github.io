---
layout: post
title: "Selenium Webdriver, a quickstart guide on Windows"
date: 2015-12-11 18:34:00
tags: selenium, java, english
---
Selenium Webdriver is a browser automation tool, widely used to implement functional and acceptance tests. It supports a variety of browsers, including headless ones like PhantomJS.
But how easy is it to setup a project and run Selenium?  
We'll discover in this article. I prepared a full working project that you can clone from [Github: selenium-windows-quickstart](https://github.com/darugnaa/selenium-windows-quickstart/).

# Java binding
Selenium has "bindings" for many programming languages: Python, Java, Ruby, C# and Javascript (Node). What are those "bindings"? They are language-specific client drivers, which let you control the browser from your language of choice.  
I will introduce binding for Java language.

### Firefox
Firefox is the easiest browser to set up. After installing it, the following example code will launch Firefox and open Selenium website:

    import org.openqa.selenium.WebDriver;
    import org.openqa.selenium.firefox.FirefoxDriver;

    WebDriver driver = new FirefoxDriver();
    driver.get("http://docs.seleniumhq.org/");

There is nothing else to do, Selenium will take care of everything.


**this post is a work in progress**
