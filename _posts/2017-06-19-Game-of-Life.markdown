---
layout: single
title:  "Conway's Game of life"
date:   2017-06-19 00:19:20 +0530
excerpt: Interesting things about a cellular automaton
tags: game-of-life 
categories: academic
comments: true
classes: wide
header:
  teaser: https://lh3.googleusercontent.com/yQ8ObYsYyB3HICwomrUSND_08Bek_bje215uaTSA1Myb2iYT-UNyBpexUvUxDTS6gmp4VEuOXO3pIrrjupLqDpez__cQXxA8n2FejUHlD3Sn_RqAe3XpkmNQ8-vAlqAjrI5s-knz8bY=w2400
---
I read Richard Dawkins' amazing book called 'The Greatest Show on Earth'
some time back. Recently, while doing a course in Linguistics, I came
across the term 'generative system' applied to language, which took me
back to something called 'Conway's Game of Life', which was also used by
Dawkins in his book to illustrate a particular point; that (very) simple rules could lead to complex entities, so countering the creationist argument that the simple rules
governing genetics and molecular biology couldn't have led to the
immense diversity seen in the natural world today.
I am writing this article having just been introduced to the world of
Conway’s Game of Life, and I hope this is a good introduction. I will
probably dive into much more detail on this topic in the near future, so
I am looking forward to that.

'Conway's Game of Life' [^1] is a cellular automaton designed by a British
mathematician, John Horton Conway, in 1970. A cellular automaton consists of:

1.  A regular grid of cells, each in one of a finite number of states
2.  Grid could be in any number of finite dimensions
3.  Each cell has a set of neighbours called its neighbourhood, defined relative to the cell
4.  An initial state is assigned by assigning a state for each cell, and a new generation is created according to some fixed rule that determines the new state of each cell in terms of the current state of the cell and the cells in the neighbourhood.

The concept of a cellular automaton was first studied by John von Neumann and Stanislaw Ulam at Los Alamos in the 1940s. They were interested in finding a hypothetical machine that could build copies of itself and succeeded. However, the set of rules that they came up with was extremely complicated, and John Conway created the Game of Life in an attempt to simplify those rules.

So the Game of Life is an example of a cellular automaton. It takes place on an infinite two-dimensional grid of
square cells. Each cell can be in two states, dead or alive. It evolves
in turns. The state of any cell in the subsequent turn is decided by the
state of the eight neighbouring cells in the current turn, according to
certain rules. The rules are:

1.  Any live cell with less than two live neighbours in the current turn
    dies in the next turn (underpopulation).
2.  Any live cell with two or three live neighbours in the current turn
    lives in the next turn.
3.  Any live cell with more than three live neighbours in the current
    turn dies in the next turn (overpopulation).
4.  Any dead cell with exactly three live neighbours in the current turn
    becomes a live cell in the next turn (reproduction).

Thus, given an initial state (called seed) the grid evolves according to
the rules and gets to subsequent states. The evolution is completely
determined by the initial state.

These simple rules lead to an almost bewildering variety of things that
can happen, only a small fraction of which I will talk here.

-   Still life - these do not change at all from turn to turn.
    Examples are...

    -   Block [^2]
        
        ![Block](https://upload.wikimedia.org/wikipedia/commons/thumb/9/96/Game_of_life_block_with_border.svg/66px-Game_of_life_block_with_border.svg.png)

    -   Boat [^2]

        ![Boat](https://upload.wikimedia.org/wikipedia/commons/thumb/7/7f/Game_of_life_boat.svg/82px-Game_of_life_boat.svg.png)

    -   Loaf [^2]

        ![Loaf](https://upload.wikimedia.org/wikipedia/commons/thumb/f/f4/Game_of_life_loaf.svg/98px-Game_of_life_loaf.svg.png)

-   Oscillators - these evolve from an initial state and come back to
    the original state after a certain number of turns. Examples are…

    -   Period 2

        -   Blinker [^2]

            ![Blinker](https://upload.wikimedia.org/wikipedia/commons/9/95/Game_of_life_blinker.gif)

        -   Toad [^2]

            ![Toad](https://upload.wikimedia.org/wikipedia/commons/1/12/Game_of_life_toad.gif)

        -   Beacon [^2]

            ![Beacon](https://upload.wikimedia.org/wikipedia/commons/1/1c/Game_of_life_beacon.gif)

        -   Traffic light - this consists of 4 blinkers [^3]

            ![Traffic Light](http://www.ericweisstein.com/encyclopedias/life/gifs/trafficl.gif)

    -   Period 3

        -   Pulsar [^2]

            ![Pulsar](https://upload.wikimedia.org/wikipedia/commons/0/07/Game_of_life_pulsar.gif)

        -   Maltese Cross [^3]

            ![Maltese Cross](http://www.ericweisstein.com/encyclopedias/life/gifs/maltescr.gif)

        -   Pressure cooker [^3]

            ![Pressure Cooker](http://www.ericweisstein.com/encyclopedias/life/gifs/pressure.gif)

    -   Period 15

        -   Pentadecathlon [^4]

            ![Pentadecahethlon](https://upload.wikimedia.org/wikipedia/commons/f/fb/I-Column.gif)

    -   Period 30

        -   Eureka [^3]

            ![Eureka](http://www.ericweisstein.com/encyclopedias/life/gifs/eureka.gif)

    -   Period 60

        -   Toadsucker - This consists of a Hassler and a toad. A
            Hassler is basically an oscillator that alternatively
            changes a properly placed object, and then changes it back
            to the original state. The object that the Hassler interacts
            with is in this case a toad, which we met in our examples
            for a period 2 oscillator. [^3]

            ![Toadsucker](http://www.ericweisstein.com/encyclopedias/life/gifs/toadsuck.gif)

-   Spaceships - these move across the square grid as they evolve. They
    are classified on the basis of their speed. Given the rules, it can
    be shown that the maximum speed achievable by a moving object in
    this world is one tile per second. In analogy with the real world,
    this could be termed as c. It is also known that Life has all
    possible spaceships that can move in any rational direction at an
    arbitrarily slow pace, but until May 2010, only spaceships that move
    in orthogonal or diagonal directions were known. The maximum speed
    for a spaceship is c/2 orthogonally, c/4 diagonally and so on for
    other slope values. For now, the following are examples of
    spaceships based on velocity:

    -   c/2

        -   Lightweight spaceship [^2]

            ![Lightweight spaceship](https://upload.wikimedia.org/wikipedia/commons/3/37/Game_of_life_animated_LWSS.gif)

    -   c/4

        -   Glider [^2]

            ![Glider](https://upload.wikimedia.org/wikipedia/commons/f/f2/Game_of_life_animated_glider.gif)

    -   c/5

        -   Spider [^3]

            ![Spider](http://www.ericweisstein.com/encyclopedias/life/gifs/spider.gif)

-   Glider guns - It is a pattern consisting of a main part that repeats
    periodically, and periodically emits a spaceship. The period of the
    gun is a multiple of the period of spaceship production. There is an interesting story about the
    glider gun. Its existence implies that initial patterns with a
    finite number of cells can eventually lead to configurations with an
    infinite number of cells. John Conway conjectured that such a thing
    was impossible but Bill Gosper discovered the Gosper Glider Gun in
    1970, winning \$50 from Conway.[^5]

    ![Gosper Glider Gun](https://upload.wikimedia.org/wikipedia/commons/e/e5/Gospers_glider_gun.gif)

I guess this qualifies as an introduction to Conway’s Game of Life. If you want to see more such objects, check out [Eric Weisstein's Treasure Trove of the Life Cellular Automaton](http://www.ericweisstein.com/encyclopedias/life/).
There are many fascinating details about the Game that I have got a slight
introduction to and which I shall read and describe in subsequent posts.
I will probably read about the proofs of certain results that I have
mentioned above, and also look into the proof that certain cellular automata are Turing complete, which is a result that I find extremely cool!

FUN FACT: If you search for Conway’s Game of Life on Google, you will
find an Easter egg - the search results page has a simulation of the
game in the corner. Do check that out! [^6]

***
[^1]: Almost all information in this article obtained from Wikipedia pages [Cellular Automaton](https://en.wikipedia.org/wiki/Cellular_automaton), [Conway's Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) and [Eric Weisstein's Treasure Trove of the Life Cellular Automaton](http://www.ericweisstein.com/encyclopedias/life/).
[^2]: Open Source image from Wikimedia Commons.
[^3]: Image from [Eric Weisstein's Treasure Trove of the Life Cellular Automaton](http://www.ericweisstein.com/encyclopedias/life/)
[^4]: Image under Creative Commons License from Wikimedia Commons. [Link](https://commons.wikimedia.org/wiki/File:I-Column.gif)
[^5]: Image under GNU Free Documentation License from Wikimedia Commons. [Link](https://commons.wikimedia.org/wiki/File:Gospers_glider_gun.gif)
[^6]: Link [here](https://www.google.co.in/search?q=conway%27s+game+of+life)
