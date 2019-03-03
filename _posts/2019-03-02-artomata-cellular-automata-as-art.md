---
layout: post
title:  Artomata&#58; Cellular Automata as Art
date:   2019-02-22
---

![Lightly Rough Bleeding Heart](/assets/img/Lightly_Rough_Bleeding_Heart.png){: .small}

I have been working on a fun art project lately. I call it *artomata*. I came up with the idea once while I was thinking about [cellular automata](https://en.wikipedia.org/wiki/Cellular_automaton), and how cool they were. [Stanislaw Ulam](https://en.wikipedia.org/wiki/Stanislaw_Ulam) and [John von Neumann](https://en.wikipedia.org/wiki/John_von_Neumann) first introduced the concept of cellular automata in the 1940s. It is an idea rooted in mathematics but expressed in at least a few natural systems (if not a great many), such as this sea snail shell:

![cellular automaton on a shell](https://upload.wikimedia.org/wikipedia/commons/7/7d/Textile_cone.JPG)

The most famous example of a cellular automaton is [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life). This "game" (which is not really a game at all, or more technically a [zero-player game](https://en.wikipedia.org/wiki/Zero-player_game)) consists of a grid of cells. Each cell can be either "alive" or "dead". When "playing" this game, you can initialize the grid with some alive cells. This is the first "generation". Each subsequent generation of the game is determined by applying the rules of the game to the current generation. I won't describe the rules here, but you can read more about it if you're interested. Basically, whether a cell is dead or alive in the next generation depends on how many of its current neighbors are dead or alive. What's fascinating about this game is that very complex patterns can emerge from a rather simple set of rules.

![Conway's Game of Life](https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif)

Conway's Game of Life is cool, but it is just the tip of the iceberg when it comes to cellular automata. Stephen Wolfram, for example, has done extensive research on cellular automata and has written a [book](https://en.wikipedia.org/wiki/A_New_Kind_of_Science) which discusses them in depth. (Disclaimer: this book is sitting on my shelf but I have not read it yet.) The [wikipedia page](https://en.wikipedia.org/wiki/Cellular_automaton) on cellular automata describes some of the ways the idea can be generalized. For example, the cells need not be square. It was this realization that inspired me to create artwork using cellular automata. I call my first cellular automaton the *pentaflower*. It is implemented as a [javascript library](https://github.com/tyleryasaka/artomata/tree/master/packages/pentaflower-svg) which can render pentaflowers in various states and colors into your browser as svg images.

![Monthly Jealous Corydalis](/assets/img/Monthly_Jealous_Corydalis.png)

The pentaflower consists of a grid of pentagons. The neighbors of each cell are the pentagons with which it shares an edge. The center cell has 5 neighbors, but all others have 3 neighbors. I wrote my code such that the rules can be adjusted, but by default the rule is that a cell is alive in the next generation if it currently has exactly 1 neighbor that is alive. If it has no alive neighbors, or if it has multiple alive neighbors, then it will be dead in the next generation.

You can see the rules in action by going [here](http://www.artomata.io/pentaflower/create?rings=20&generation=0&color1=%23FFFFFF&color2=%232E2E2E&color3=%23010101) and incrementing the value of *Generation* by 1 at a time. When you load the page it will be set to 0. By setting it to 1, then 2, then 3, etc., you can see the progression of the rules through each generation . Additionally, by setting the values of *Rings* (how big the grid should be) and the colors, many beautiful patterns can be created. You can see a gallery of some patterns I have made on [the artomata website](http://www.artomata.io/pentaflower). You can also use [this page](http://www.artomata.io/pentaflower/create?rings=20&generation=0&color1=%23FFFFFF&color2=%232E2E2E&color3=%23010101) to make pentaflowers of your own.

If you're interested in learning about how the pentaflower names are generated, you can see [this post]({% post_url 2019-03-02-naming-my-pentaflowers %}).

Time permitting, I am hoping to continue the artomata project in my free time, possibly utilizing different geometric shapes and other variations on cellular automata, such as non-binary states.

[artomata.io](http://www.artomata.io)
