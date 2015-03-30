<p align='right'><a href='http://code.google.com/p/ruletablerepository/source/list?path=/wiki/RoadMap.wiki'>Detailed page changes</a></p>

Looking further ahead, here's a sketch of how the [rule table format](TheFormat.md) might be extended to support future CA (see also: FutureWork).

  * Items in bold are those supported in Golly.
  * Items marked with <b><code>**</code></b> are supported in a Golly emulation script: `Scripts/Python/RuleTableToTree.py`.

These are just some ideas - please edit or comment to add your opinions. For a good survey on neighborhoods, see http://cell-auto.com/neighbourhood/

<h2>Two-dimensional neighborhoods</h2>

| neighborhood | transitions | symmetries | image |
|:-------------|:------------|:-----------|:------|
| <b>vonNeumann</b> | `c,n,e,s,w : c'` | <b>none</b>, rotate2, rotate (<b>rotate4</b>), rotate\_reflect (<b>rotate4reflect</b>), <b>reflect_horizontal</b> (<b>reflect</b>), reflect\_vertical, <b>permute</b> | http://ruletablerepository.googlecode.com/files/vonNeumann.PNG |
| <b>Moore</b> | `c,n,ne,e,se,s,sw,w,nw : c'` | <b>none</b>, rotate2, <b>rotate4</b>, <b>rotate8</b>, <b>rotate4reflect</b>, <b>rotate8reflect</b>, <b>reflect_horizontal</b> (<b>reflect</b>), reflect\_vertical, direction\_permutation, total\_permutation (<b>permute</b>) | http://ruletablerepository.googlecode.com/files/moore.PNG |
| <b>hexagonal</b> (see HexagonalNeighborhood) | `c,n,e,se,s,w,nw : c` | <b>none</b>, <b>rotate2</b>, <b>rotate3</b>, <b>rotate6</b>, <b>rotate6reflect</b>, <b>permute</b> | http://ruletablerepository.googlecode.com/files/hexagonal.PNG |
| <b>triangularVonNeumann<sup>**</sup></b> | `c,n1,n2,n3 : c'` | <b>none<sup>**</sup></b>, <b>rotate<sup>**</sup></b>, <b>rotate_reflect<sup>**</sup></b> (<b>permute<sup>**</sup></b>) | http://ruletablerepository.googlecode.com/files/triangularVonNeumann.PNG |
| <b>triangularMoore<sup>**</sup></b> | `c,n1..n12 : c'` | <b>none<sup>**</sup></b>, <b>rotate<sup>**</sup></b>, <b>rotate_reflect<sup>**</sup></b>, layer\_permutation, total\_permutation (<b>permute<sup>**</sup></b>) | http://ruletablerepository.googlecode.com/files/triangularMoore.PNG |

<h2>Two-dimensional partitioning schemes</h2>

| neighborhood | transitions | symmetries | image |
|:-------------|:------------|:-----------|:------|
| <b>Margolus<sup>**</sup></b> (see MargolusNeighborhood) | `a,b,c,d : a',b',c',d'` | <b>none<sup>**</sup></b>, rotate (<b>rotate4<sup>**</sup></b>), rotate\_reflect (<b>rotate4reflect<sup>**</sup></b>), <b>reflect_horizontal<sup>**</sup></b>, <b>reflect_vertical<sup>**</sup></b>, <b>permute<sup>**</sup></b> | http://ruletablerepository.googlecode.com/files/Margolus.GIF |
| <b>square4_cyclic<sup>**</sup></b>, <b>square4_figure8h<sup>**</sup></b>, <b>square4_figure8v<sup>**</sup></b> (==square4\_reading\_order) (see MargolusNeighborhood) | `a,b,c,d : a',b',c',d'` | <b>none<sup>**</sup></b>, <b>rotate4<sup>**</sup></b>, <b>rotate4reflect<sup>**</sup></b>, <b>reflect_horizontal<sup>**</sup></b>, <b>reflect_vertical<sup>**</sup></b>, <b>permute<sup>**</sup></b> | http://ruletablerepository.googlecode.com/files/Square4.GIF |
| square9\_reading\_order | `a,b,c,d,e,f,g,h,i : a',b',c',d',e',f',g',h',i'` | none, rotate, rotate\_reflect, reflect\_horizontal, reflect\_vertical, permutation | http://ruletablerepository.googlecode.com/files/Square9.GIF |

<h2>One-dimensional neighborhoods and partitioning schemes</h2>

| neighborhood | transitions | symmetries | image |
|:-------------|:------------|:-----------|:------|
| <b>oneDimensional</b> | `c,w,e : c'` | <b>none</b>, <b>reflect</b> (<b>permute</b>) | http://ruletablerepository.googlecode.com/files/1dRadius1.PNG |
| oneDimensional\_radius2 | `c,w2,w,e,e2 : c'` | none, reflect, permutation? | http://ruletablerepository.googlecode.com/files/1dRadius2.PNG |
| oneDimensional\_partition2 ([brick wall](http://cell-auto.com/neighbourhood/brickwall/index.html)) | `a,b : a',b'` | none, reflect | http://ruletablerepository.googlecode.com/files/BrickWall.GIF |

<h2>Larger two-dimensional neighborhoods</h2>

| neighborhood | transitions | symmetries | image |
|:-------------|:------------|:-----------|:------|
| vonNeumann\_radius2 | `c,n,e,s,w,N,E,S,W : c'` | none, rotate2, rotate4, rotate4reflect,  reflect\_horizontal, reflect\_vertical, layer\_permutation, total\_permuation | http://ruletablerepository.googlecode.com/files/vonNeumannRadius2.PNG |
| diamond\_radius2 | `c,n,ne,e,se,s,sw,w,nw,N,E,S,W : c'` | none, rotate2, rotate4, rotate4reflect,  reflect\_horizontal, reflect\_vertical, layer\_permutation, total\_permuation | http://ruletablerepository.googlecode.com/files/diamondRadius2.PNG |
| star\_radius2 | `c,n,ne,e,se,s,sw,w,nw,N,NE,E,SE,S,SW,W,NW : c'` | none, rotate2, rotate4, rotate4reflect,  reflect\_horizontal, reflect\_vertical, layer\_permutation, direction\_permutation, layer\_direction\_permutation, total\_permuation | http://ruletablerepository.googlecode.com/files/starNeighborhood.PNG |
| disc\_radius2, or<br> circle_radius2 <table><thead><th> <code>c,n,ne,e,se,s,sw,w,nw,N,NNE,ENE,E,ESE,SSE,S,SSW,WSW,W, : c'</code> </th><th> none, rotate2, rotate4, rotate4reflect, reflect_horizontal, reflect_vertical, layer_permutation, total_permuation </th><th> <a href='http://ruletablerepository.googlecode.com/files/intermediateRadius2.PNG'>http://ruletablerepository.googlecode.com/files/intermediateRadius2.PNG</a> </th></thead><tbody>
<tr><td> Moore_radius2 </td><td> <code>c,n,ne,e,se,s,sw,w,nw,N,NNE,NE,ENE,E,ESE,SE,SSE,S,SSW,SW,WSW,W,WNW,NW,NNW : c'</code> </td><td> none, rotate2, rotate4, rotate8, rotate4reflect, rotate8reflect, reflect_horizontal, reflect_vertical, layer_permutation, total_permuation </td><td> <a href='http://ruletablerepository.googlecode.com/files/mooreRadius2.PNG'>http://ruletablerepository.googlecode.com/files/mooreRadius2.PNG</a> </td></tr></tbody></table>

<h2>Three-dimensional neighborhoods</h2>

<table><thead><th> neighborhood </th><th> transitions </th><th> symmetries </th><th> image </th></thead><tbody>
<tr><td> vonNeumann3D </td><td> <code>c,x+,x-,y+,y-,z+,z- : c'</code> </td><td> none, rotate, rotate_x, rotate_y, rotate_z, reflect_x, reflect_y, reflect_z, rotate24, rotate24reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/3dVonNeumann2.PNG'>http://ruletablerepository.googlecode.com/files/3dVonNeumann2.PNG</a> </td></tr>
<tr><td> Moore3D </td><td> <code>c,n1..n26 : c'</code> </td><td> none, rotate4, rotate8, rotate4_x, rotate4_y, rotate4_z, rotate8_x, rotate8_y, rotate8_z, reflect_x, reflect_y, reflect_z, rotate24, rotate24reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/3dMoore.PNG'>http://ruletablerepository.googlecode.com/files/3dMoore.PNG</a> </td></tr>
<tr><td> faceCentredCubic </td><td> <code>c,n1..n12 : c'</code> </td><td> none, rotate12, rotate24, rotate24reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/FCC.PNG'>http://ruletablerepository.googlecode.com/files/FCC.PNG</a> </td></tr></tbody></table>

<h2>Exotic neighborhoods</h2>

<table><thead><th> neighborhood </th><th> transitions </th><th> symmetries </th><th> image </th></thead><tbody>
<tr><td> Penrose P3 tiling </td><td> <code>c,n1..n4 : c'</code> </td><td> permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/Penrose.PNG'>http://ruletablerepository.googlecode.com/files/Penrose.PNG</a> </td></tr>
<tr><td> <a href='http://en.wikipedia.org/wiki/Demitesseractic_honeycomb'>F4_lattice</a> </td><td> <code>c,n1..n16 : c'</code> </td><td> none, rotate192, rotate192reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/F4lattice.PNG'>http://ruletablerepository.googlecode.com/files/F4lattice.PNG</a> </td></tr>
<tr><td> <a href='http://en.wikipedia.org/wiki/Icositetrachoric_honeycomb'>D4_lattice</a> </td><td> <code>c,n1..n24 : c'</code> </td><td> none, rotate192, rotate192reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/D4lattice.PNG'>http://ruletablerepository.googlecode.com/files/D4lattice.PNG</a> </td></tr>
<tr><td> <a href='http://en.wikipedia.org/wiki/E8_lattice'>E8_lattice</a> </td><td> <code>c,n1..n240 : c'</code> </td><td> none, rotate348364800, rotate348364800reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/E8.PNG'>http://ruletablerepository.googlecode.com/files/E8.PNG</a> </td></tr>
<tr><td> <a href='http://en.wikipedia.org/wiki/Leech_lattice'>Leech_lattice</a> </td><td> <code>c,n1..n196560 : c'</code> </td><td> none, rotate8315553613086720000, rotate8315553613086720000reflect, permutation </td><td> <a href='http://ruletablerepository.googlecode.com/files/leechLattice.PNG'>http://ruletablerepository.googlecode.com/files/leechLattice.PNG</a> </td></tr></tbody></table>

Brian Prentice and others have done some work on CA that run on arbitrary tilings: <a href='http://linuxenvy.com/bprentice/TiledCA/TiledCA.html'>http://linuxenvy.com/bprentice/TiledCA/TiledCA.html</a>

There are some sets of cellular automata that are best supported independently, rather than incorporating them into rule tables:<br>
<br>
<br>
<table><thead><th> Rule set </th><th> Parameters </th></thead><tbody>
<tr><td> <b>Life-like</b> </td><td> b0..b8,s0..s8 </td></tr>
<tr><td> <b>Generations</b> </td><td> b0..b8,s0..s8,n </td></tr>
<tr><td> Larger than Life </td><td> range,bMin,bMax,sMin,sMax </td></tr></tbody></table>


The final rule, Larger than Life, relies on large neighborhoods; these are not currently supported by Golly. Mirek's Cellebration (MCell) is one program capable of running these rules.<br>
<br>
CA on Penrose tilings have been intensively investigated by Susan Stepney et al.<br>
<br>
Many of these concepts, and much more, have been covered in Andrew Adamatzky's book, Game of Life Cellular Automata (Springer, 2010).