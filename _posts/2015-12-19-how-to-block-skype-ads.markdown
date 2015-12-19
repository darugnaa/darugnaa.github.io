---
layout: post
title: "How to block Skype's ads"
date: 2015-12-19 19:19:19
tags: skype, adblock
---
Skype probably is the most famous voice and video call software. In its latest versions the main window, called "Skype Home", usually shows some gigantic and irritating advertisement.

This is how it looks like. Skype also is quite memory hungry.  
<img src="http://i.imgur.com/9HQiY59.png?1">

Fortunately there's a way to block ads inside Skype (and save some RAM too). Ads are downloaded after the program startup, so we just need to block the addresses used.  
**1.** Locate the "hosts" file: `/etc/hosts/` on \*nixes, `%SystemRoot%\system32\drivers\etc\hosts` on Windows.  
**2.** Open the "hosts" file with a text editor (Notepad on Windows will work). Run the editor as administrator.  
**3.** Add the following lines and save the file

    # Block Skype banner ads
    127.0.0.1   rad.msn.com
    127.0.0.1   g.msn.com
    127.0.0.1   live.rads.msn.com

**4.** Only for Windows: click "Start", then "Run", paste this command: `ipconfig /flushdns` and click OK.  
**5.** Start Skype and enjoy the ad-free "Skype Home".

<img src="http://i.imgur.com/nxkIXNb.png">
As a bonus, RAM usage has decreased a little =)  
This technique works on all Operating Systems. Different Skype versions may show "Skype Home not available" instead of not displaying the banner.
