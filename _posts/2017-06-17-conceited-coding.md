---
layout: post
title:  "Conceited Coding: How to Get Started"
date:   2017-06-17
---

If you're interested in making yourself appear to be an intellectually superior badass and belittle your peers, here's what you do:

1. Become a coder
2. Learn obscure language hacks that minimize readability and maximize references to internal language constructs and syntactic quirks.
3. Use said tricks to "improve" your team's codebase, making sure to indicate their superiority over any of your coworker's ideas.

I'll give you a couple examples from JavaScript.

Here's one:

```
!!
```

That's the so-called ["cast-to-bool"](https://stackoverflow.com/questions/784929/what-is-the-not-not-operator-in-javascript#comment4717995_784929) operator (which, mind you, is [not actually an operator](https://stackoverflow.com/questions/784929/what-is-the-not-not-operator-in-javascript#comment2597265_784946)). It coerces any value to a boolean. Your inferior coworker probably wanted to use a straightforward and readable solution like `Boolean()`, or (heaven forbid) not even do any type conversion at all and instead just let the `if` statement perform the implicit type conversion. What can I say - this trade secret is not not the greatest thing since the linux kernel.

I'll give you one more:

```
+ new Date()
```

Believe it or not, we're not doing any addition here. That is the more obscure and less readable alternative to `Date.now()`, which returns the current timestamp.

Now, I can't take credit for either of these 2 freebies. The first was introduced to me by someone making a pull request to one of my old lame open source widgets or something. The second [has over 3k upvotes on stack overflow](https://stackoverflow.com/a/221297/4376543).
