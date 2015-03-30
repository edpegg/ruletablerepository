## What needs to change? ##

If you look at RoadMap you'll see that the rule table format now supports quite a few neighborhoods, including partitioning ones. And the extension to 3D etc. is sketched out and doesn't look problematic.

To avoid bloating the format, we must be careful not to include too much. Some things we **don't** want are:
  * world specifications: size, wrap-around, etc.
  * display parameters: color, icons, etc.
These things will vary with each implementation and belong elsewhere.

The one remaining big problem is that many CA are best expressed as something other than a list of rule cases - often a bit of C++/Java/etc. code is shorter, neater, easier to maintain, and faster to execute. (For some of those rules we can use Tom Rokicki's rule tree compiler - see `Rules/TreeGenerators` and `Scripts/Python/make-ruletree.py` - but these only work if the total input-space is sensibly traversable - for high numbers of states and large neighborhoods it is too slow: a 40-state Moore-neighborhood CA has 2.6E+14 inputs to consider.) To avoid everyone programming their rules in different languages, other CA formats (see TheFormat) developed mini-languages of their own for the conditionals and simple functions. Whether we end up supporting one of those languages in Golly, or making our own, or doing something else entirely, is undecided.

As a test case, consider emulating [MCell's LavaLamp](http://psoup.math.wisc.edu/mcell/rullex_cycl.html). It's a 3-state `neighborhood:Moore_radius2` CA with permutation symmetry and is quite easy to express as a rule table. It could be emulated quite easily using a 81-state Moore-neighborhood CA (similar to TriLife on TheRules). But the rule has `3^25 = 8.4E+11` inputs to consider; no existing approach of using rule tables, or RuleTreeGen, or RuleTableToTree will work. And yet we could code a custom Golly algorithm for it quite straightforwardly and it would run perfectly fast.

## Format proposals: ##

  * RoadMap : an overview of things we might support
  * PermutationSymmetry
  * Calcyman's suggestions for other neighbourhoods: GenericNeighborhoods
  * UnboundVariables
  * MargolusNeighborhood
  * HexagonalNeighborhood
  * AlansIdeas

## Website issues: ##

  * GollyAccessPoint : a common area to store Golly-compatible files