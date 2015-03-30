# Introduction #

Variables behaved differently in the original rule-table implementation in Golly.  Variables were originally "unbound" and could be re-used within a single rule line.  This was abandoned to make it easier to support the Tempesti rule.  By contrast, we now need up to eight identical variables for each set of states.  Here's a quick example:
```
  n_states:2
  ...
  var a={0,1}

  1,a,a,a,a,a,a,a,a,0
```
currently unpacks into two rules:
```
  1,0,0,0,0,0,0,0,0,0
  1,1,1,1,1,1,1,1,1,0
```

But with "unbound a={0,1}", the same line `1,a,a,a,a,a,a,a,a,0` would unpack into 2^8=256 different rules -- 1-cells with all possible combinations of 0 and 1 neighbors would go to 0.  This is not a particularly useful example -- but the "unbound" option would significantly simplify a good number of existing rule tables.


# Details #

If conciseness in rule tables is an important enough goal -- and I think maybe it is, for writability as well as readability -- then unbound variables could be brought back as an option. Here's a bigger sample showing the effect of both UnboundVariables and PermutationSymmetry.  In HistoricalLife, we'd need two variables instead of fifteen:

```
  var a={0,2}
  var b={0,2}
  var c={0,2}
  var d={0,2}
  var e={0,2}
  var f={0,2}
  var g={0,2}
  var i={0,1,2}
  var j={0,1,2}
  var k={0,1,2}
  var l={0,1,2}
  var m={0,1,2}
  var n={0,1,2}
  var o={0,1,2}
  var p={0,1,2}

  f,1,1,1,a,b,c,d,e,1
  1,1,1,a,b,c,d,e,g,1
  1,i,j,k,l,m,n,o,p,2
```

Bound variables could still be defined with "var ... = {...}", so all existing rule tables would still work -- but many of them could be revised to make them much smaller and more readable:

```
  unbound OFF={0,2}
  unbound ANY={0,1,2}

  OFF,1,1,1,OFF,OFF,OFF,OFF,OFF,1
  1,1,1,OFF,OFF,OFF,OFF,OFF,OFF,1
  1,ANY,ANY,ANY,ANY,ANY,ANY,ANY,ANY,2
```

I think it would be significantly easier for someone new to Golly to use this last rule table as a template for creating a new rule of their own. (?)

Tim Hutton has written:

> Personally I don't mind having a few extra variables, and I think
> having both types would be a bit confusing but of course it's an open
> project so lets proceed by consensus.

Consensus sounds good, and I'll be happy to try for it before digging into ruletable\_algo.cpp again -- anything to avoid that project, in fact!

But I don't think two types would be too confusing in practice.  People learning the ropes by reading a sample .table file probably wouldn't even see the bound "var" form, because it would only be used in the Tempesti .table and a few other places.