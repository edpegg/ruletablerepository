Golly supports the hexagonal neighborhood since version 2.2.

### Use: ###

An example:

```
# Frank Buss' life-like totalistic hexagonal CA:

n_states:3
neighborhood:hexagonal
symmetries:permute

var a={0,1,2}
var b={a}
var c={a}
var d={a}
var e={a}
var f={a}

var i={0,1}
var j={i}
var k={i}
var l={i}

var m={0,1,2}

0,2,0,0,0,0,0,2
c,1,2,0,0,0,0,1
c,2,2,i,j,k,l,1
c,2,2,2,i,j,k,2
m,a,b,c,d,e,f,0
```

Compare with [his implementation](http://www.frank-buss.de/automaton/hexautomaton.html):

```
if (s1 == 0 && s2 == 1 && center == 0) {
	result = 2;
} else if (s1 == 1 && s2 == 1) {
	result = 1;
} else if (s2 == 2) {
	result = 1;
} else if (s2 == 3) {
	result = 2;
} else {
	result = 0;
}
# s0, s1 and s2 are the number of color 0, 1 and 2 on the six neighbour fields. s0 is not used in the rule set.
```

### Features: ###

  * Supported symmetries: **none**, **rotate2**, **rotate3**, **rotate6**, **rotate6reflect**, **permute**.
  * Rendering isn't handled correctly in Golly, the whole grid is on a slant. Improving this is on our task list.

### Previous discussion: ###

We should be able to define the format for the hexagonal neighborhood quite easily, and write a Golly script that converts it to a Moore neighborhood rule table.


The hexagonal neighborhood is used by a number of rules. For example, Frank Buss has made an interesting 3-state totalistic rule in the hexagonal neighborhood. The hexagonal neighborhood is a subset of the Moore neighborhood, which means it can be emulated directly in Golly, without any more states. That seems okay, doesn't it?

However, the rule tables end up being much larger than necessary. Because there is no 'hexagonal' symmetry to deal with this, or even a 'rotate2' symmetry, every possible permutation has to be programmed separately. For example, Frank Buss' CA is as follows:

```

n_states:3
neighborhood:Moore
symmetries:none

var a={0,1,2}
var b={0,1,2}
var c={0,1,2}
var d={0,1,2}
var e={0,1,2}
var f={0,1,2}
var g={0,1,2}
var h={0,1,2}

var i={0,1}
var j={0,1}
var k={0,1}
var l={0,1}

var m={0,1,2}



#First Condition

0,2,0,0,a,0,0,0,b,2
0,0,2,0,a,0,0,0,b,2
0,0,0,2,a,0,0,0,b,2
0,0,0,0,a,2,0,0,b,2
0,0,0,0,a,0,2,0,b,2
0,0,0,0,a,0,0,2,b,2



#Second Condition

c,1,2,0,a,0,0,0,b,1
c,2,1,0,a,0,0,0,b,1
c,2,0,1,a,0,0,0,b,1
c,2,0,0,a,1,0,0,b,1
c,2,0,0,a,0,1,0,b,1
c,2,0,0,a,0,0,1,b,1

c,1,0,2,a,0,0,0,b,1
c,0,1,2,a,0,0,0,b,1
c,0,2,1,a,0,0,0,b,1
c,0,2,0,a,1,0,0,b,1
c,0,2,0,a,0,1,0,b,1
c,0,2,0,a,0,0,1,b,1

c,1,0,0,a,2,0,0,b,1
c,0,1,0,a,2,0,0,b,1
c,0,0,1,a,2,0,0,b,1
c,0,0,2,a,1,0,0,b,1
c,0,0,2,a,0,1,0,b,1
c,0,0,2,a,0,0,1,b,1

c,1,0,0,a,0,2,0,b,1
c,0,1,0,a,0,2,0,b,1
c,0,0,1,a,0,2,0,b,1
c,0,0,0,a,1,2,0,b,1
c,0,0,0,a,2,1,0,b,1
c,0,0,0,a,2,0,1,b,1

c,1,0,0,a,0,0,2,b,1
c,0,1,0,a,0,0,2,b,1
c,0,0,1,a,0,0,2,b,1
c,0,0,0,a,1,0,2,b,1
c,0,0,0,a,0,1,2,b,1
c,0,0,0,a,0,2,1,b,1



#Third Condition

c,2,2,i,a,j,k,l,b,1

c,2,i,2,a,j,k,l,b,1
c,i,2,2,a,j,k,l,b,1

c,2,i,j,a,2,k,l,b,1
c,i,2,j,a,2,k,l,b,1
c,i,j,2,a,2,k,l,b,1

c,2,i,j,a,k,2,l,b,1
c,i,2,j,a,k,2,l,b,1
c,i,j,2,a,k,2,l,b,1
c,i,j,k,a,2,2,l,b,1

c,2,i,j,a,k,l,2,b,1
c,i,2,j,a,k,l,2,b,1
c,i,j,2,a,k,l,2,b,1
c,i,j,k,a,2,l,2,b,1
c,i,j,k,a,l,2,2,b,1



#Fourth Condition

c,2,2,2,a,j,k,l,b,2
c,2,2,i,a,2,k,l,b,2
c,2,2,i,a,j,2,l,b,2
c,2,2,i,a,j,k,2,b,2

c,2,i,2,a,2,k,l,b,2
c,i,2,2,a,2,k,l,b,2
c,2,i,2,a,j,2,l,b,2
c,i,2,2,a,j,2,l,b,2
c,2,i,2,a,j,k,2,b,2
c,i,2,2,a,j,k,2,b,2

c,2,i,j,a,2,2,l,b,2
c,i,2,j,a,2,2,l,b,2
c,i,j,2,a,2,2,l,b,2
c,2,i,j,a,2,k,2,b,2
c,i,2,j,a,2,k,2,b,2
c,i,j,2,a,2,k,2,b,2

c,2,i,j,a,k,2,2,b,2
c,i,2,j,a,k,2,2,b,2
c,i,j,2,a,k,2,2,b,2
c,i,j,k,a,2,2,2,b,2



#Fifth Condition

m,a,b,c,d,e,f,g,h,0

```


How inefficient is that? If you visit [his website](http://www.frank-buss.de/automaton/hexautomaton.html), you will see how simply the rule is defined.

Also notice that two of the elements are set to _**a**_ and _**b**_ in every rule, since the neighborhood actively ignores these cells.


Ideally, with the hexagonal neighborhood, we would have symmetries such as:

  * none
  * rotate6
  * reflect
  * rotate6reflect


Look how much the rotate6reflect could potentially compress the rule table:

```
n_states:3
neighborhood:Hexagonal
symmetries:rotate6reflect

var a={0,1,2}
var b={0,1,2}
var c={0,1,2}
var d={0,1,2}
var e={0,1,2}
var f={0,1,2}

var i={0,1}
var j={0,1}
var k={0,1}
var l={0,1}

var m={0,1,2}



#First Condition

0,2,0,0,0,0,0,2



#Second Condition

c,1,2,0,0,0,0,1
c,1,0,2,0,0,0,1
c,1,0,0,2,0,0,1



#Third Condition

c,2,2,i,j,k,l,1
c,2,i,2,j,k,l,1
c,2,i,j,2,k,l,1



#Fourth Condition

c,2,2,2,i,j,k,2
c,2,2,i,2,j,k,2
c,2,i,2,j,2,k,2



#Fifth Condition

m,a,b,c,d,e,f,0
```


From 72 rule tables to just 11 is an immense improvement by anyone's standards.

> Brilliant stuff. All I've got to add is that it looks like we really need a PermutationSymmetry for cases like this. Oh, and I wonder if with some suitable slanted hexagon .icons whether the hex nhood will look reasonable in Golly. If you do put any time into a script to perform the emulation step then please consider how possible permutation would be - if it works then we can port it to the main Golly implementation for other cases. --TJH

> I agree. An emulation script would definitely be very helpful. It would be even more helpful if this was implemented. Most hex rules would look much less distorted and more symmetrical. --TCK(The new member)

> Since this page was written, Andrew Trevorrow has implemented the "HexBuss" rule using make-ruletree.py, please see the recent golly-test messages. I think there are some changes afoot that will make issues of rule table format less important in cases like this - we'll be writing our rules in python perhaps and having them automatically converted to rule trees. --TJH

Here's Andrew's Python version of the rule:
```
name = "HexBuss"
n_states = 3
n_neighbors = 8
def transition_function(s):
   # s[0..8] are cell states in the order NW, NE, SW, SE, N, W, E, S, C
   # but we ignore the NE and SW corners to emulate a hexagonal grid:
   #             NW N NE         NW  N
   #             W  C  E   ->   W  C  E
   #             SW S SE         S  SE
   
   # set n1 and n2 to the number of neighbors in states 1 and 2
   n1 = 0
   n2 = 0
   for i in xrange(8):
      # ignore s[1] and s[2]
      if i < 1 or i > 2:
         if s[i] == 1: n1 += 1
         if s[i] == 2: n2 += 1
   
   if s[8] == 0 and n1 == 0 and n2 == 1:
      return 2
   elif n1 == 1 and n2 == 1:
      return 1
   elif n2 == 2:
      return 1
   elif n2 == 3:
      return 2
   else:
      return 0
```

> I've gone off the idea of doing any sort of automatic conversion.  The latest version of make-ruletree.py is so easy to use that any attempt to automate the process would just make things unnecessarily complicated.  I personally find it much easier to create .tree files (via make-ruletree.py) rather than .table files, so I think this method should somehow be given more prominence.  Perhaps we need a RuleTrees.wiki page (with a link from the front page) where we can discuss this alternative format and describe how to use make-ruletree.py.  Or if people don't like Python, there are  Java, Perl and C++ examples in the Rules/TreeGenerators subdir. --AKT

Support has now been added for both the hexagonal neighborhood and the permute symmetry, so the HexBuss rule table can now look like this:

```
n_states:3
neighborhood:hexagonal
symmetries:permute

var a={0,1,2}
var b={0,1,2}
var c={0,1,2}
var d={0,1,2}
var e={0,1,2}
var f={0,1,2}

var i={0,1}
var j={0,1}
var k={0,1}
var l={0,1}

var m={0,1,2}

0,2,0,0,0,0,0,2
c,1,2,0,0,0,0,1
c,2,2,i,j,k,l,1
c,2,2,2,i,j,k,2
m,a,b,c,d,e,f,0
```

I just put this here as an example; I agree with Andrew's point that for rules like this a Python (or other language) implementation of the rule (to be used with make-ruletree.py) is often a more natural way to express it. But this example hints at where you might want a rule table for more complex rules which would otherwise need too many if-statements if written in Python. --TJH