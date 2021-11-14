---
layout: post
title: Things To Do With A BCI
tags: bci
---

Here's a bunch of disorganized thoughts, which may or may not be remotely feasible.

## Data over Space vs Time

So. The big problem with BCIs right now is that it's really hard to get a lot of bits
of data out of the brain at once.

Like, ... oh, I'll just get RZTD's words on the subject.

{% include dynamo.html 
    nick="Renzao Tudou" user="@rztd:dynamo.obsolete.tech" url="/general/hardware/bci" 
    content="
the problem now is that i really cant control more than about 4 
lights at once. so. i figure instead of giving myself headaches trying to
control more lights, i write code to track the bits over time.

for example. it would be terrible to try to control enough
bits for the 60-odd keys on a keyboard. you would need `⌈2⍟60` = 6 keys for
just the data, plus some final bit to send the HID packet on a rising edge. nightmare.

instead, i could use my four bits over *time*. if i program it to check 3 time slices
at a time, i could get `4*3` = 64 possibilities. i would need some extra data probably
to encode timing info (or i could just have it on a timer). not bad.
"
%}

Yeah, what they said.

### The Problem With That

is that it's so *slow*. Like last I checked RZTD couldn't switch bits more than about every 10 seconds.
Meanwhile, I typed this sentence with my boring ol' human hands in less than a minute, and that included
thinking of what to write.

I assume their solution works great for disabled people who can't type and who don't have a better
option ... but there's already technologies for that and they are way better than 30 seconds per character,
like tracking where you're looking on a keyboard and such.

## Hybrid Approach

So, what if you combined nimble fingers with thought?

For example, you could map some popularly-used but out of the way keys to a mental signal.
Mostly I'm thinking of the shift key of course. Last I heard it's many times faster to adroitly change one or 
two bits than 4 (for RZTD at least), so you could definitely squeeze out some WPM that way.

If you can do a couple bits fast on the fly, you could hook it up to other modifier keys. 
I don't use Emacs, but I could imagine mapping all the `meta` and `ctrl` and whatever to BCI bits.
And you could do something similar with Vim and `esc`, or a leader key.

## Predictive Algorithms

I hate to break out the buzzwords, but it's also possible you could gather many many brain signals, which you can't control
very well, and feed them to a learned network or something which would filter and process the outputs for more
fidelity.

We touched on this kind of thing in my neuroscience class. It's not a new idea; in fact I think there's a whole 
300-level course on it here, and the readings we did were *old* (so old they still called them "neural networks").
The main problem is you boot the problem of training from your brain to the learned network, and it's really hard
to make training data.

---

So yeah. BCIs currently suck.

Hopefully I can do my part to make them suck less.
