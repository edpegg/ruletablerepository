# 1 #
Have several of items at the top of the .table file.

```
n_states: 20
grid: yes
space: euclidean
sides: 4
dimentions: 2
neighborhood: Moore
symmetries: rotate4
radius: 2
```

A neighbourhood could then be constructed without the need for too many differnt types.
  * What is 'grid'? -- TJH
    * CA's that line up nodes (cells) in a grid. In a practical sence this will always be "yes". -- AT
      * What's the alternative? -- TJH
        * Perhaps none for now, I don't know. It could be not used while using the rest of the framework. -- AT
  * How would non-Euclidean spaces be defined? -- TJH
    * Hyperbolic space for example. -- AT
      * The space of possible 2D tilings where each cell is the same regular polygon (although we could also consider more general [tessellations](http://en.wikipedia.org/wiki/Tessellations)) is given by a table of [Schläfli symbols](http://en.wikipedia.org/wiki/Schl%C3%A4fli_symbol) {p,q}. The pairs {3,6}, {4,4} and {6,3} are the three normal grids. Five smaller pairs give the five platonic solids which we're probably not interested in. Larger values (e.g. {7,3} - the packing of heptagons with three around each vertex) are hyperbolic. So having a simple flag saying 'space:euclidean' or 'space:hyperbolic' isn't that useful - it's not specific enough. (I've put a table of (2D) Schlafli symbols in a blog post: [here](http://ferkeltongs.livejournal.com/28364.html).) -- TJH
        * A bit over my head but sounds good, clearly you have put more thought into the details than me. I also thought btw that you could distort hyperbolic space so that the outside was streched out to greater and greater size as you go further from the center of mapping a triangle on the figure to a rectangular screen to stop the sizes of the cells becoming smaller as you go into the distance that is away from the center of the screen -- AT
        * Agreed. Define the lattice as the form {_D_,_S_}, where _D_ is the number of dimensions and _S_ is the set of _D_ Schlafli symbols. The lattice is the most fundamental property of a CA, followed by the neighbourhood. -- APG
  * What does 'sides' mean? -- TJH
    * Most CA's use a 4 Sided grid but one in particular uses a 7 sided grid requiring hyperbolic rendering to draw it, there are also 6 sided hexagonal grids and 3 sided grids that work on standard space. 1D CA's are 2 sided grids. -- AT
      * That's one parameter (p) of the Schläfli table, we'd need q as well in order to define the space. What is the 7-sided grid example you mention? -- TJH
        * Margensterns Trains found somewhere here http://uncomp.uwe.ac.uk sorry thats a bit vaugue as I can't remember exactly what link I found it in. I thought of the name based on it's creator and the terminology used in it's description as Margenstern didnt seem to think it needed a name. I also made a proof of concept for some aspects of the movement of the train in an RT. I presume we don't need this feild then as it can be merged with the D&S stuff in the space type feild -- AT
          * [Margenstern's papers](http://www.lita.univ-metz.fr/~margens/research.html). [This one](http://portal.acm.org/citation.cfm?id=771537) talks about trains, and links to some of his other papers that might be relevant. -- TJH
        * I assume that he means Order-3 heptagonal tiling (see Wikipedia). -- APG
          * No, sorry I meant: what is the rule? -- TJH
            * I believe that it's called "Morgenstern's Trains". -- APG
  * Also I can see several problems with this approach - it doesn't adapt to the partitioning neighborhoods very well, for example, and some of these headers won't make sense with some CA. The advantage of our current set of headers (n\_states,neighborhood,symmetries) is that they apply to all possible CA, as far as we can tell. -- TJH
    * The options in 'Neighborhood' depends on some of the others but other that that it is quite simple and consistant. Give me a CA that either in Golly or not yet avalible and I will tell you the set-up for it. -- AT
      * [square4\_cyclic](http://code.google.com/p/ruletablerepository/wiki/RoadMap)? You could just specify `neighborhood:square4_cyclic` as in the RoadMap proposal but then many of your other parameters will be redundant and just add confusion. With our current proposal, if we want to add a {7,3} neighborhood it wouldn't be too hard - we could just say `neighborhood:hyperbolic_7_3` for example - I don't see a problem with adding neighborhoods as we need them, since making an all-powerful scheme from the outset will add a lot of confusing complexity. And in any case, hyperbolic CA are hugely problematic to implement in terms of cell storage and rendering, so it's not a high priority I wouldn't think. I really appreciate your input though, it is a useful discussion to be having. -- TJH
        * If it is square4\_cyclic it will still be a 4 sided (or what the D&S way of saying this) grid and will still have 4 dimentions with a radius of 1. Remembering the structure of the neighborhood naming and what is avalible and what wont work will be more complicated than constantly dividing it up, unless you implement a system like myne but with underscores as feild delimiters -- AT
# 2 #
Documenting parts of patterns by selecting rectangular groups of cells and applying text to them that apear after zooming in past a 1:1 zoom as a fixed size at a fixed or relative orentation to the box, like a label. The box itself could have thin or\and subtley coloured borders.

The text for them would be stored in the RLE or MC file.

  * Controll click drag to create, right click them choose delete from dropdown menu to remove (or similar). I know there are coding issues with how UI is drawn atm though.
    * This suggestion isn't anything to do with rule table files though - you should seek support for this idea on the golly list, not here. Or implement it yourself so we can see an example of what you mean. -- TJH
      * I can't code it into Golly but do you want me to create a fake screenshot or two to show how it could work? List pointed me here. -- AT
        * Did the list point you here? I don't see that email. I don't think the RTR is the right place to discuss this. -- TJH
          * Sorry, I'm sure I saw it in my email, want me to remove this or more prefrably move it somewhere else? Also see my reply to this question in the next point. -- AT
            * No need to remove it. All discussion is welcome - it's just that we should keep this website focussed on the approach of using rule tables, so this discussion will be better served elsewhere. -- TJH
# 3 #
I'm not sure if this is my method or an obvious algebraic method or even if it definitely works but here goes.

It's based on something similar I did for Minesweeper that did work, inspired by something I read online about suprisingly long distance behaviour in certain Minesweeper configuations.

Start with a simple example from WireWorld.
http://mathworld.wolfram.com/WireWorld.html

Lets say for simplicity:

```
000
133
000
```

According to the rules of WireWorld this will progress as so.

```
000
213
000
```

```
000
321
000
```

```
000
332
000
```

```
000
333
000
```

As the signal travels down the wire

First create (a map?) for each state that changes.

All

```
000
133
000
```

State 1

```
000
100
000
```

State 2

```
000
000
000
```

And assign letters to each cell in each map.

All

```
abc
def
ghi
```

State 1

```
rst
uvw
xyz
```

State 2

```
ABC
DEF
GHI
```


Construct the algebraic formulae (square brackets = subscript).

```
a[0] = 0

...

I[0] = 0
```

Skip a to i for this next part.

```
r[n] = (0 < s[n-1] + u[n-1] + v[n-1] < 3)

...

I...
```

Now you can re-arrange the equation to ask questions like for example, does this cell ever become state 1 or what are all the possibilites for the previous generation that could lead to this one.

And specifically code could be written into Golly to do this.
  * I don't really understand your suggestion but either way there's nothing stopping you using this kind of notation in your own tools (e.g. python scripts) before compiling them down to rule tables or rule trees. We decided early on that we didn't want to support [CDL](http://www.jcasim.de/)-style expression languages - and so far we haven't been regretting that decision - even Wireworld is reasonably simple to read in the rule table format. -- TJH
    * I don't mean a way to change the rule table format, I mean a way to perform other functions in Golly. For example a user could request extra information about a cell. For example cell (100, 120) could currently be state 3, and it could be determined that after running the CA for an infinite length of time it would eventually become at some point state 4 and 6 but never states 0, 1, 2, 3 or 5 without actucally having to run the CA forever to find out. --AT
      * Ah, OK, you're not talking about rule tables. So again this isn't really the right place to discuss this. Why don't you knock up a demo to explore whether this idea would be useful? -- TJH
        * Please let me store the idea here for now. -- AT
        * The demo would involve simplifying any algebraic equation. The coding is beyond me. -- AT
          * Alan, if you can effect your suggestion in polynomial time then you would win the P=NP? problem, which is worth **$1 000 000 USD**. Good luck! -- APG
            * Therefore it probbably dosn't do it in polynomial time. -- AT
              * I don't think it can be done at all in a time faster than iterating  all the way (brute-force). I think this problem is a variation of the [Entscheidungsproblem](http://en.wikipedia.org/wiki/Entscheidungsproblem) where the formal language is English and the mathematical statement is something like "Given a <insert boring description of cellular automata> where <insert boring rules of WireWorld>, the cell at (x, y) will be state 1 for at least one point in time" c -- MJ
                * You need the pattern in there as well. -- AT