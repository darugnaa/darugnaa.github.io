---
layout: post
title:  "How to fold code regions with Netbeans"
date:   2016-07-20 20:30:00
tags: coding, java
---
In C# language you can surround a block of code with `#region` / `#endregion` [preprocessor directive](https://msdn.microsoft.com/en-us/library/9a1ybwek.aspx).

`#region` lets you specify a block of code that you can expand or collapse when using the outlining feature of the Visual Studio Code Editor. In longer code files, it is convenient to be able to collapse or hide one or more regions so that you can focus on the part of the file that you are currently working on.  

Java misses such functionality. While any IDE collapses methods or classes, there's no unique way to collapse more methods together.  
In Netbeans we can define a folding region using custom crafted comments in Java source code:

    //<editor-fold desc="Add your description">
    ... your Java code here
    //<editor-fold>
    
The result is pretty much the same as Visual Studio.

Unfolded code: <img src="img/2016-07-20-fold-before.png" alt="Unfolded code" />

Folded code: <img src="img/2016-07-20-fold-after.png" alt="Folded Java code! Well done, Netbeans!" />

This way we can group togeter related methods, collapse getters/setters, collapse loops inside big methods and in general manage code readability.

However, a folding region defined as above is displayed as a comment in Eclipse...

There's a shortcut to insert a code fold in the editor: just type `fcom` and press TAB key.
