What is the Margolus neighborhood?

  * http://cell-auto.com/neighbourhood/margolus/
  * http://psoup.math.wisc.edu/mcell/rullex_marg.html

### Use: ###

Here is an example:

```
# Diffusion Limited Aggregation, in a Margolus neighborhood CA

n_states:3
neighborhood:Margolus
symmetries:rotate4reflect

# In the Margolus nhood, the transition a,b,c,d : e,f,g,h means:
#  a  b     -->    e  f
#  c  d            g  h

# 0: vacuum
# 1: gas particle
# 2: stuck particle

# HPP gas rules:
1,0,0,0 : 0,0,0,1 # a diagonally-travelling particle keeps going
1,1,0,0 : 0,0,1,1 # two particles pass through each other
0,1,1,0 : 1,0,0,1 # two particles collide head-on
1,1,1,0 : 0,1,1,1 # three particles pass through each other

# plus aggregation rules: (these seem to suffice)
1,0,2,0 : 2,0,2,0
1,0,2,2 : 2,0,2,2
```

And another:

```
# A simple CA simulation of sand - inspired by MCell's version.

n_states:4
neighborhood:Margolus
symmetries:reflect_horizontal

# In the Margolus nhood, the transition a,b,c,d : e,f,g,h means:
#  a  b     -->    e  f
#  c  d            g  h

# 0 : air
# 1 : sand
# 2 : wood
# 3 : magical source of sand

var a={0,1,2}
var b={0,1,2}

1,1,0,0 : 0,0,1,1 # a pair of sand particles falls
1,a,0,b : 0,a,1,b # otherwise, sand falls next to a static column
1,0,a,0 : 0,0,a,1 # otherwise, it can topple
3,0,0,0 : 3,0,1,0 # sand can appear from the magical source
```

### Features: ###

  * Golly doesn't currently support the Margolus neighborhood directly, but it can be emulated using the Moore neighborhood - use [Scripts/Python/Rule-Generators/RuleTableToTree.py](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/Rule-Generators/RuleTableToTree.py?view=markup).
  * Supported `neighborhood` types: **Margolus**, **square4\_figure8v**, **square4\_figure8h**, **square4\_cyclic**. See [Tim Tyler's page](http://cell-auto.com/neighbourhood/margolus/) for an explanation of these, and [Patterns/Margolus/Sand-Test.rle](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Patterns/Margolus/Sand-Test.rle?view=markup) for an example.
  * Supported symmetries: **none**, **reflect\_horizontal**, **reflect\_vertical**, **rotate4**, **rotate4reflect**, **permute**.
  * See [Scripts/Python/glife/ReadRuleTable.py](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/glife/ReadRuleTable.py?view=markup) and [Scripts/Python/glife/EmulateMargolus.py](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/glife/EmulateMargolus.py?view=markup) for implementation details.
  * A colon separator performs exactly the same job as the comma but makes it easier to read. (We now also support this for the other neighborhoods, to separate outputs from inputs but it's especially useful here.)

### Discussion: ###

  * reflect\_horizontal (and vertical) are new symmetries that we were missing.
  * It's longer than MCell's specification string but much more powerful, allowing multiple states and variables, and different symmetries. And no-change transitions can be skipped, so it's actually more readable.
  * We could use Calcyman's GenericNeighborhoods for the header but is there any need to? This approach is more human-readable, which is the main point of the rule table format - we want people to start authoring their own rules, as they have been!

Tim Tyler discusses the [Square-4 neighborhood](http://cell-auto.com/neighbourhood/square4/index.html) which is related to the Margolus neighborhood. It is actually more appropriate than the Margolus neighborhood for the Sand CA above, since it covers one particular case where 2 stacked sand particles should topple but don't. See the pattern info in [Patterns/Margolus/Sand-Test.rle](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Patterns/Margolus/Sand-Test.rle?view=markup) for an example that shows the effect of these different neighborhoods. --TJH