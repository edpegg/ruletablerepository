## Examples: ##

Example 1:
```
# Roger Banks' 1971 CA for universal computation (Banks-I)
n_states:2
neighborhood:vonNeumann
symmetries:rotate4reflect
111000
011101
011111
```

Example 2:
```
# Signals (2/3) pass alongside a wire (1):
n_states:4
neighborhood:vonNeumann
symmetries:rotate4
var a={2,3}
var b={2,3}
var c={2,3}
a,0,b,1,c,b
```

## Specification: ##

Files in the .table format are in plain ASCII text. Each line is one of the following six types:

  1. Comment lines are empty or start with a "#".
  1. `n_states:` (followed by an integer) specifies the number of cell states in the CA (from 0 to n-1 inclusive).
  1. `neighborhood:` specifies the cell neighborhood for the CA update. See RoadMap for the list of supported neighborhoods.
  1. `symmetries:` specifies the spatial symmetries that apply to the transitions listed. See RoadMap for the symmetries supported by each neighborhood.
  1. Variables (`var`) allow transitions to be compactly written using text labels that stand for multiple states.
  1. Transitions consist of variable labels and cell states, specifying the inputs and outputs of each transition. Together the set of transitions specifies the behaviour of the CA.

Important points to note:

  * Valid symmetries depend on the neighborhood. For example, the `Moore` neighborhood can have the following symmetries: `none`, `rotate4`, `rotate8`, `reflect`=`reflect_horizontal`, `rotate4reflect`, `rotate8reflect`, `permute`.
  * The three lines that specify `n_states`, `neighborhood` and `symmetries` should appear before the variables and transitions.
  * Variables should appear before the first transition that uses them. For clarity they usually appear before the transitions.
  * The entries in a transition are separated by commas. An exception to this is when `n_states` is 10 or less and when no variables are used - in this case no comma should be used, as in Example 1 above. This exception is to allow the 'traditional' list of transitions to be used.
  * The neighborhood type determines the number of entries in the transitions. E.g.:
    * `vonNeumann`: C,N,E,S,W,C'
    * `Moore`: C,N,NE,E,SE,S,SW,W,NW,C'
    * `Margolus`: a,b,c,d : a',b',c',d' (see MargolusNeighborhood)
  * Comments can appear on the same line as transitions, preceded by a "#".
  * Where the same variable appears more than once in a transition, it stands for the same state each time - they are _bound_. The output of a transition can contain variables but only if those variables also appear in the inputs (the output must be fully defined).
  * Rule tables usually don't specify every possible set of inputs. For those not listed, the input cells remain unchanged.
  * Rules are checked in the order given in the file - the first rule that matches is applied. If you want, you can write rules in the form of general cases and exceptions, as long as the exceptions appear first in the file.

Since Golly version 2.2:
  * Single-state variables are now permitted as the output of a transition.
  * Variables can now be used inside later variables.
  * Comments can now be written after a variable declaration.

> _Golly also has a page describing the format: [.table format](http://golly.cvs.sourceforge.net/viewvc/*checkout*/golly/golly/src/Help/formats.html#table)_

### Worked example: ###

The following rule table has rotational symmetry and one variable:
```
n_states:6
neighborhood:vonNeumann
symmetries:rotate4
var a={1,2}
0,a,3,4,5,a
```

If we expand out the variable we get the following equivalent rule table:
```
n_states:6
neighborhood:vonNeumann
symmetries:rotate4
013451
023452
```

If we also expand out the rotate4 symmetry:
```
n_states:6
neighborhood:vonNeumann
symmetries:none
013451
034511
045131
051341
023452
034522
045232
052342
```

All three of these rule tables are exactly equivalent.

## About the development of the format: ##

(TJH wrote:)

There are other CA rule table formats out there. The simplest is just to list the transitions. Codd and Langton used this method, where e.g. 012345 stands for the transition:
<tt><pre>
1<br>
4 0 2    --->     5<br>
3<br>
</pre></tt>
The inputs are given in the order: centre, north, east, south, west, followed by the updated centre state. For CA that only use states 0-9, no separator is required, so each transition is just a sequence of 6 digits. The .table format supports this, and also the Moore neighborhood version: C,N,NE,E,SE,S,SW,W,NW,C'. For CA with more than 10 states, commas are used to separate the entries.

Rather than list every transition, we can skip transitions that make no change to C. We can also skip transitions that are rotated or reflected versions of ones already listed. (More on this later.)

However, for more complex CA, including von Neumann's original 29-state CA, this is not sufficient. Too many transitions would have to be listed. Most CA programs get around this by hard-coding the transition tables, as C++ or Java or whatever. This is fine and good but not future-proof. If someone gave you a stack of rules for your new CA engine you'd have to carefully translate each one into your desired language.

Wolfram uses a different approach for identifying elementary CA: code the transition table into the bits of a number. [Rule 110](http://en.wikipedia.org/wiki/Rule_110), for example, encodes the transition table in its name. MCell uses a similar approach for its [Margolus notation](http://www.mirekw.com/ca/rullex_marg.html). The problem here is that for more complex CA involving more states or larger neighborhoods this approach soon stops being useful as the encoded string becomes too long.

A different problem was encountered when considering some other rule table formats: [CDL](http://www.jcasim.de/), cellang (I've never seen any details but I think it's not dissimilar) and CAXL (likewise). CDL, for example, is an entire programming language, and adding support for this to your favourite CA program would be a significant amount of work. There has to be a simpler way to encode rule tables that is both reasonably compact and easy to understand and use, for the majority of popular CA rules. And there is!

The XLife program has the .r format, e.g. [codd.r](http://www.filewatcher.com/p/xlife-5.0-1.i386.rpm.211831/usr/lib/xlife/codd/codd.r.html), where square brackets are used for multiple states. E.g. `0000[45]0` stands for the transitions <tt>0,0,0,0,4 -> 0</tt> and <tt>0,0,0,0,5 -> 0</tt>. This is a big leap forwards, allowing rule tables to be expressed in a reasonably compact form. The problem is that it doesn't provide enough compression.

The adopted solution can be found in Gianluca Tempesti's [thesis](http://lslwww.epfl.ch/pages/embryonics/thesis/AppendixA.html) - using variables to stand for multiple states. Then, e.g. for a={1,2,3}, the rule <tt>1,a,3 -> a</tt> would stand for three rules at once: <tt>1,1,3 -> 1</tt> and <tt>1,2,3 -> 2</tt> and <tt>1,3,3 -> 3</tt>. This method gives all the compression of the XLife approach and then some more on top.

If you have a C/C++ implementation of a transition function, there is a way to automatically produce a rule table file. See make-ruletable.cpp for instructions.

> _The format still needs work. Discuss extensions and improvements here: FutureWork_

## Comparison of rule table formats: (work in progress) ##

  * [CDL](http://www.jcasim.de/) Jorg's 2003 paper on translating CDL into C or Java: [link](http://www.complex-systems.com/abstracts/v14_i02_a04.html)
  * cellang
  * CAXL (some discussion of these above)
  * DDLab's .vco format (mentioned [here](http://www.cogs.susx.ac.uk/users/andywu/multi_value/spiral_rule.html))
  * CAMEL/CARPET
  * CLANG
  * WINALT
  * CELLAB (I've only heard mention of these four: http://www2.computer.org/portal/web/csdl/doi/10.1109/HCC.2003.1260224)
  * XLife's .r format (see above)
  * Golly's .tree format