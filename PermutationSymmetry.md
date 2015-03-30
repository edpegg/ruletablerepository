The permute symmetry has been supported in Golly since version 2.2, both directly (for the vonNeumann, Moore, hexagonal and oneDimensional neighborhoods) and via [Scripts/Python/RuleTableToTree.py](http://golly.cvs.sourceforge.net/viewvc/golly/golly/src/Scripts/Python/Rule-Generators/RuleTableToTree.py?view=markup) for all the [others](https://code.google.com/p/ruletablerepository/wiki/RoadMap).

# Use: #

The permute symmetry simply means that we ignore the order of the input neighbor cells, as in the Game of Life.

An example:

```
# Historical Life
#
# A rule by Dave Greene
# Translated by Calcyman

n_states:3
neighborhood:Moore
symmetries:permute

# 0 : cell was never alive
# 1 : live cell
# 2 : cell was alive at some point in the past

var a={0,2}
var b={a}
var c={a}
var d={a}
var e={a}
var f={a}

var h={0,1,2}
var i={h}
var j={h}
var k={h}
var l={h}
var m={h}
var n={h}
var o={h}

h,1,1,1,a,b,c,d,e,1   # exactly 3-neighbors: birth or survival
1,1,1,a,b,c,d,e,f,1   # living cell has exactly 2-neighbors: survives
1,h,i,j,k,l,m,n,o,2   # otherwise, living cell dies and becomes the history state
```

# Previous discussion: #

Many rule tables, for example Life, are much larger than necessary. There are only really 3 rules (birth/survival on 3 neighbors, survival on 2 neighbors, death otherwise), whereas the rule table is comparatively huge. One way of reducing the size of a rule table would be to allow all permutations to be handled in one line, rather than a line for each permutation.

An example is my HistoricalLife table. It contains 85 useful rules, which are as follows:


56 permutations of 'birth or survival on 3 neighbors'
28 permutations of 'survival on 2 neighbors'
A rule to make on cells die and become history cells.


The new rules might be expressed like this:

```
...
f,1,1,1,a,b,c,d,e,1 interchange {N,NE,E,SE,S,SW,W,NW}
1,1,1,a,b,c,d,e,g,1 interchange {N,NE,E,SE,S,SW,W,NW}
1,i,j,k,l,m,n,o,p,2

```

DaveG:

I was surprised that I could get the 80+ rules down to just 12 by using the "rotate8" symmetry parameter; I thought I'd be wishing for the "permutation" parameter a lot more fervently!  But HistoricalLife is a fairly simple rule -- I wouldn't always be able to just sit down and list all the not-rotationally-equivalent permutations, without making mistakes.

On the other hand, what we have in Golly right now certainly seems to work pretty well.  I guess the question is pretty much the same as for UnboundVariables:  how many new rules are people going to want to write?  and how user-friendly do we want to make the process of creating new rules?

TJH:

Can I suggest that permutation symmetry would work like this:

```
# Historical Life
#
# A rule by Dave Greene
# Translated by Calcyman

n_states:3
neighborhood:Moore
symmetries:permute
# (was 'permutation' but I chose 'permute' to match 'rotate', 'reflect' etc.)

var a={0,2}
var b={0,2}
var c={0,2}
var d={0,2}
var e={0,2}
var g={0,2}
var f={0,1,2}

var i={0,1,2}
var j={0,1,2}
var k={0,1,2}
var l={0,1,2}
var m={0,1,2}
var n={0,1,2}
var o={0,1,2}
var p={0,1,2}

f,1,1,1,a,b,c,d,e,1   # 3-neighbor birth or survival
1,1,1,a,b,c,d,e,g,1   # 2-neighbor survival
1,i,j,k,l,m,n,o,p,2   # Otherwise, On state dies and becomes the history state
```

Then 'permutation' is just another symmetry alongside reflections and rotations. This approach is less useful if the permutation symmetry applied to some transitions and not others but I haven't seen an example of this yet. We still have unknown implementation issues with adopting the permutation symmetry but it looks attractive.


APG:
That _does_ make things a lot simpler. But the 'interchange' approach can be used for other symmetries, like the hexagonal symmetry:

`interchange {N,NE,E,S,SW,E}`

Or the _Ben's rule_ symmetry (also used in the MRM rule table):

`interchange {N,E,S,W}{NE,SE,NW,SW}`

Maybe we should just add a symmetry type when required.

> We now have support (`Scripts/Python/RuleTableToTree.py`) for a 'permute' symmetry, and it seems to be working very well - you can try the rule table above! (I've worked out how to apply permutation-respecting-duplicates _after_ substituting the variables, which means I don't need to generate all `numNeighbors!` (factorial) rules for each transition, only those permutations for which the inputs were different.) As part of the same code I've added a HexagonalNeighborhood too, which addresses one of APG's points. --TJH