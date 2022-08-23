---
layout: post
title: ADΔER Codec
description: My new library for event-based video representations
image: /assets/images/posts/rust/out_16bit_2_c10.jpg
terminal: /assets/images/posts/rust/out_16bit_2_c10.jpg
vsraw: /assets/images/posts/rust/out_16bit_2_c10.jpg
vssmart: /assets/images/posts/rust/out_16bit_2_c10.jpg
---
<meta name="image" property="og:image" content="{{ page.image }}">
<img src="{{ page.image }}" class="center" width="384" height="216">
## ADΔER Codec

![out_16bit_2_c10.jpg]({{site.baseurl}}/_posts/out_16bit_2_c10.jpg)

I'm excited to share a software library I've been working on called the **ADΔER codec**. ADΔER stands for Address, Decimation, Δt Event Representation, which I'm pitching as a radical new way to think about video. This Rust library enables users to experiment with my asynchronous, event-driven video representation, and build applications which leverage it. To showcase some of my ideas, I put together a [demo](https://yt-embed.herokuapp.com/embed?v=yfzwn5PrMpw) with examples of transcoding framed video to ADΔER. I have a couple applications in the works which directly employ this library, which I hope to share in the coming months. 

This work is the culmination of three years of research into event video representations, but does not encompass all the work I've done. Rather, this is just the stuff that I polished up to a state where I felt comfortable releasing it out into the wild. I needed the pressure of making my code public in order to get it to a state where it's at least somewhat documented and readable. More is coming soon, especially as I approach a paper deadline in October! In the meantime, refer to the project's README for more information, and star/watch it on [GitHub](https://github.com/ac-freeman/adder-codec-rs) to receive updates. And of course, let me know if you have any questions by contacting me directly or creating an issue on GitHub.
