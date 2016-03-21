---
layout: post
title:  "MD5 for Windows command line"
date:   2016-03-21 21:40:00
tags: command-line, windows, md5
---
Windows command line and Powershell do not have a default "md5sum" utility.
There are many third party tools or PS scripts to do such a simple task.
I prefer a pure Microsoft utility called FCIV: File Checksum Integrity Verifier.
It can be downloaded from Microsoft site: [https://support.microsoft.com/en-us/kb/841290](https://support.microsoft.com/en-us/kb/841290)  

The usage is quite simple:  
```fciv myfile.ext``` calculates the MD5 checksum of the file.  
```fciv -sha1 myfile.ext``` calculates the SHA1 checksum.  
```fciv -both myfile.ext``` calculates both hashes.

A note about the installation: fciv.exe is not added to the system path, so you must do it manually. Type in the command line: ```setx PATH "%path%;c:\fciv"``` (change C:\fciv with the path of your installation)

