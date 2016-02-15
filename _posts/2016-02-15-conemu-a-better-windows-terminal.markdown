---
layout: post
title: "ConEmu: a better windows terminal"
date: 2016-02-15 13:27:00
tags: windows, terminal
---
One of the projects I am working on lately involves a very basic Windows tool: command line terminal.  
It is rather painful to work with `cmd.exe` on Windows: no resizing, no easy copy of rows, no tabs, no coloring... so I did some research and found this gem: [ConEmu](https://conemu.github.io/).  
The description is quite interesting: *ConEmu-Maximus5 is a Windows console emulator with tabs, which presents multiple consoles and simple GUI applications as one customizable GUI window with various features*.

<img src="https://conemu.github.io/img/ConEmu-Maximus5.png" alt="ConEmu looks pretty cool!"/>

I gave it a try, it is a huge step forward. ConEmu really does it job very well in two spots I needed:

- Tabs (hit CTRL + Tab to switch between consoles) and tabs placement
- Easy selection and copy of text (not the clumsy block selection of cmd.exe) with both mouse and keyboard

Configuring tabs is not intuitive. I scratched my head a few times before figuring it out. From Settings window, go to Startup->Tasks and press `[+]` button to add a "command group", insert the following commands.
The split screen magic is done using [-new_console](https://conemu.github.io/en/SplitScreen.html) argument.

    > cmd.exe /k "%ConEmuBaseDir%\CmdInit.cmd"

    cmd.exe /k ""%ConEmuBaseDir%\CmdInit.cmd"  -new_console:s50V"
    
An alternative way would be to manually edit ConEmu's config file (default `C:\Program Files\ConEmu\ConEmu.xml`) and add the following piece:
    
    <key name="Task11" modified="2016-02-11 09:54:19" build="160124">
        <value name="Name" type="string" data="{Shells::Due}"/>
        <value name="Flags" type="dword" data="00000000"/>
        <value name="Hotkey" type="dword" data="00000000"/>
        <value name="GuiArgs" type="string" data=""/>
        <value name="Cmd1" type="string" data="&gt; cmd.exe /k &quot;%ConEmuBaseDir%\CmdInit.cmd&quot;"/>
        <value name="Cmd2" type="string" data="cmd.exe /k &quot;&quot;%ConEmuBaseDir%\CmdInit.cmd&quot;  -new_console:s50V&quot;"/>
        <value name="Active" type="long" data="1"/>
        <value name="Count" type="long" data="2"/>
    </key>
