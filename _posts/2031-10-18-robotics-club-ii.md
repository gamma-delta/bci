---
layout: post
title: More Robotics Club
date: 2031-10-18 18:40:00
tags: life robotics code raspi
---

... aww, that was sweet of Kyra, I think. (In case I delete the post, I left my computer
unattended on the table and she wrote a little blog post about it.)

I do kinda wish people wouldn't call me "guy." Not sure why... It might be because it's weirdly
informal? But I don't really mind people calling me similarly informal things.

Anyways onto brass tacks.

## What a SPIghtmare

I found a Python library to work with SPI on the Raspi called `spidev`, which seems to work.
But of course, the devil's in the details.

The documentation for the MCP3008 is very dense, but here's what I think happens.

1. Raspi activates the MCP3008 by pulling `chip select` low.
2. Raspi sends 4 bits over `MOSI` indicating which pin to gather data from and whether it's in
   "single-ended" or "differential" mode. I don't really understand differential mode
   so I'll stick with single-ended. (I think differential is for noise smoothing?)
3. MCP3008 sends 10 bits over `MISO` with the signal it reads off from the specified pin.
4. MCP3008 continually sends 0 until it's deactivated by the Raspi pulling `chip select` high.

All of this is great except for step 2. `spidev` operate on bytes, not bits. If I send one byte,
even if I only set 4 of the bits, I'll have missed 4 of the bits the MCP3008 sent.
There is an advanced `xfer` method with a `word_size` parameter but I'm not amazingly sure if I'm using it right.

Ugh. I might just cop out and go ask RZTD if they have any tips.
