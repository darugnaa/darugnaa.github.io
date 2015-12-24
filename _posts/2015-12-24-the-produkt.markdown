---
layout: post
title: "fr-08: .the .product"
date: 2015-12-24 21:37:00
tags: farbrausch, the produkt, demo, 64KiB
---
Many years have passed since I first discovered this "demo", and it still fascinates me.  
I'm not part of any "scene" and I don't remember how I stumbled upon this amazing piece of art. But sometimes I really like to watch it again.  
<img src="http://content.pouet.net/files/screenshots/00001/00001221.jpg" alt="Futuristic architecture featured in the demo - Courtesy of pouet.net">

It's an animated 3D scene rendered in DirectX, with music and credits, about 4 minutes long.  
Find it here: http://farbrausch.com/prod.py?which=17 (the download link is broken at the moment)  
Download it from here: https://files.scene.org/view/demos/groups/farb-rausch/fr08_final.zip  
What's so special about it? It's an executable file smaller than 65536 bytes. About an average .torrent file, less than a Word document, way way smaller than a mp3 song.

If you know a little about programming and 3D graphics you are going to ask yourself **how** all of this can be compressed into 64KiB. Textures take space, meshes take space, music, meta data, all takes space... compression alone isn't enough.

In [one of the dedicated sites](http://www.theproduct.de/text.html) lies the explanation. *There's no compression*.

- Textures are not stored, they are generated: the executable stores the algorithms used to paint textures. (this is done in the initial loading)
- Meshes are generated with primitives (cubes, spheres, triangles) attached together and animated.
- Music is a MIDI track rendered by synthesizer.
- The executable is stripped (all extra metadata is removed)
- Data is stored and/or packed in custom formats
- [There was still enough space for writing credits](http://www.theproduct.de/scro1.html)

It was Windows XP times when the demo came out. Now with Windows10 and DirectX11 the demo works but the full screen is cropped and I see the window title and borders ruining the black background. Anyway it's awesome. That's exactly what I admire: knowledge, hard work, good team and quality.
