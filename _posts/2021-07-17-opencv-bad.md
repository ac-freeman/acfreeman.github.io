---
published: true
layout: post
title: Ruining a Linux Installation with OpenCV
description: A short rant about OpenCV
image: /assets/images/posts/opencv-bad/logo.png
---
<meta name="image" property="og:image" content="{{ page.image }}">
<img src="{{ page.image }}" alt="OpenCV logo" class="center" style='height: 30%; width: 30%; object-fit: contain'>

OpenCV is a behemoth of a library. It's really useful, but my goodness is it a pain to work with sometimes.

This week I was trying to compile OpenCV to be able to get faster optical flow performance with CUDA. I needed to recompile OpenCV with the CUDA flags enabled. I also needed FFMPEG support to process full videos. I had upgraded my FFMPEG a few weeks ago to version [4.4](http://ffmpeg.org/download.html#release_4.4), because it was hard resetting my machine every time I tried to rescale a video (the CPU would quickly hit 100% and then crash). But apparently the latest FFMPEG update broke the OpenCV bindings. Fine, I'll downgrade FFMPEG for now and find a workaround or have another version in a container, I said. I also needed CuDNN, but I'm not sure how much that contributed to my problem.

Anyway, everything broke. I started getting all sorts of CUDA build errors, so I tried upgrading to CUDA 11.4. I tried different Nvidia drivers. I tried building older, better tested versions of OpenCV but that led to a myriad of errors related to the FFMPEG codecs not being available or having improper function definitions even though they were installed and working correctly. I spent **three days** straight trying to fix it before giving up. OpenCV was irrevocably broken, and I was tired of it. I think somewhere along the line I tried "installing" my OpenCV build with <code>make install</code>, and that can apparently cause issues with updating system packages.

I tried getting my programs running on Windows, and I got _very close_ but abandoned that for now. OpenCV and CUDA are even more difficult to work with in a CMake application on Windows. I don't want to use a full Visual Studio solution because 1) Visual Studio is bloated and I don't like it, and 2) having cross-platform code is unimportant when there's only one person working on it and using it right now (me). So I threw my hands up and decided to wipe the slate clean with a fresh Ubuntu install. 

And that worked great. Perfectly. My program runs again, on the latest version of OpenCV, compiled with CUDA, and I can continue doing the work that matters. It's just frustrating to me that OpenCV isn't more modular and user-friendly. It's so easy to break! While I'm ranting, there's an undue amount of effort put into the Python documentation, considering the library is written in C/C++. The C++ docs are terrible and most of the example code is horribly outdated. The library is way too big, and I should be able to more easily add/drop modules as I wish without having to recompile the whole thing. It's so large that it's impractical to containerize on a personal machine with limited storage. It's amazing and powerful when it works, but when it doesn't... I want to rip my hair out.
