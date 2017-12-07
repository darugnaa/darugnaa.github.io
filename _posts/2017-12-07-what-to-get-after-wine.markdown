---
layout: post
title: "What to get after Wine?"
date: 2017-12-07 16:50:00
tags: windows, linux
categories: idea
---
What to get after Wine? I'm not talking about drinks, but instead I will talk
about the [Wine project](https://www.winehq.org/). The project is a kind of
"emulator" that let you run Windows applications on Linux.  
It is not a real emulator, like the name itself explains with a nice [recursive
acronym](https://en.wikipedia.org/wiki/Recursive_acronym): _Wine Is Not an Emulator_.
It's a compatibility layer that translates Windows system calls to Linux ones,
so the applications really believe to be run inside Windows ;-)

This is so much of a cool idea that Microsoft did the same thing backwards:
[Windows Subsystem for Linux](https://msdn.microsoft.com/en-us/commandline/wsl/about).
I would have expected a joke involving drinks or desserts, at least.

After installing WSL from Control Panel, I downloaded Ubuntu bash from
Microsoft Store. Python and Ruby work perfect!  
I'm running [Jekyll](https://jekyllrb.com/docs/windows/) and [Jupyter]
(https://www.digitalocean.com/community/tutorials/how-to-set-up-a-jupyter-notebook-to-run-ipython-on-ubuntu-16-04) on my Windows10 laptop.

Bash terminal runs on its own Linux like filesystem, to get accesso to the
computer's disk simply navigate to `/mnt/c/` directory.

I'm very surprised of this Microsoft product. It is not clear to me _why_ they
decided to support another Operating System architecture in Windows
(maybe the popularity of Cygwin?).
