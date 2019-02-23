---
layout: post
title:  The IEEE Standard 754
date:   2019-02-22
---

I recently dug up a presentation I did as an undergrad back in 2015 for my *Programming Languages* course. The task was to do a 2-minute "elevator pitch" for the [IEEE 754 floating-point standard](https://en.wikipedia.org/wiki/IEEE_754). I took some liberties with the assignment and proceeded to perform the following "rap". I can't guarantee that it's 100% technically correct, but if you're as nerdy as me you might get a kick out of it.

Coincidentally, I just discovered that it fits almost perfectly over [this karaoke version](https://youtu.be/awHmEWQPDxE) of *The Fresh Prince of Bel-Air*.

{% highlight text %}
The I-triple-E standard seven fifty four
Floating points represented and efficiently stored
Pick a number – any number – it's composed of three
Essential components in the I-triple-E
First there's the sign, this is just a single bit
Is it negative or not? That's all there is to it
Next we've got the mantissa, also called significand
Without this value, our number would be bland
If you take a given number and eliminate the dot
And round it to precision, the mantissa's what you've got
But what happened to that dot? That's the final component
It scales our mantissa and it's called the exponent
Add a bias when you store it, on retrieval subtract
Raise your base to that power to make an impact
With these three components, many numbers you can store
But there are a few exceptions that we need to explore
In binary mantissas, leading ones can be implied
With the exception of zero – it has no ones to hide!
So we use a special case, no need to be a hero
The mantissa and exponent are both set to zero
Likewise we can handle infinity and beyond
Mantissa bits off and exponent bits on
Not a Number (NaN) can be represented by
A mantissa non-zero and exponent bits high
The I-triple-E standard seven fifty four
Representing your numbers on the CPU core
{% endhighlight %}
