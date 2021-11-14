---
layout: post
title: BCI Devkit Arrived!
tags: bci robotics code life electronics
---

It's here!

I'm writing this quickly before I go to robotics club and I'm gonna show everyone.

I don't really know if I want to think of a demo or something? That sounds kinda pretentious
and I have no idea what I would show off besides. I think I'll try and get just one sensor up and running today
I can stick it high on my forehead apparently and it will work well enough. The one time I like my hairline.

---

OK, post-club Brian here. That was a blast but really frusturating.

So. RZTD's devkit apparently just outputs binary signals, so I assumed mine would too. And I assumed you could just
hook up the sensors to the GPIO pins.

So. The problem is that the sensor board outputs *analog* signals, while the raspberry pi only accepts *digital*.
In addition you can't just wire the sensors to the GPIO and rely on it being over some voltage to be interpreted as a `1`
because the maximum voltage the kit outputs isn't enough to count as a `1`, and there's some electronics reason
you shouldn't do that anyways even if the voltage was high enough (something about "floating pins").

Kyra told me to look into an ADC chip, or analog to digital converter. Also, a breadboard. Also, a hair tie so I don't
keep getting my hair caught in things.

This will be my first time working with actual electronics since this old Snap Circuits kit I found in my uncle's attic.
Should be exciting!

... as if I had plenty of spare free time.
