<b>Table of Contents:</b>



---


## News ##
  * <b>10th Feb 2013:</b> Georgi Gochev reports a new 2-state 2-color relative-movement non-halting busy beaver: 7.735 billion steps.
  * <b>8th Feb 2013:</b> Georgi Gochev reports a new 2-state 2-color relative-movement non-halting busy beaver: 240 million steps.
  * <b>6th Feb 2013:</b> New 2-state 2-color relative-movement non-halting busy beaver: 18.22 million steps.
  * <b>1st Feb 2013:</b> Ed Pegg, Jr. asks: "What is the longest a machine can run before it becomes predictable? For Langton's Ant, it's around 10000 steps. For Worm Trails, it's 4 million. What 2-color, 2-state turmites are unresolved? Is there a list somewhere?" I've made a new section: Non-halting Busy Beavers
  * <b>26th Aug 2011:</b> Georgi Gochev reports a new record Busy Beaver for 5-state 2-color absolute-movement on a square grid, now up to 25 billion steps.
  * <b>12th Jan 2011:</b> Georgi Gochev reports a new record Busy Beaver for 5-state 2-color absolute-movement on a square grid, now up to 7.1 billion steps.
  * <b>6th July 2010:</b> Georgi Gochev reports a new record Busy Beaver for 5-state 2-color absolute-movement on a square grid, now up to 1.8 billion steps.
  * <b>4th June 2010:</b> Georgi Gochev reports a new record Busy Beaver for 5-state 2-color absolute-movement on a square grid.

## Introduction ##

[Turing machines](http://en.wikipedia.org/wiki/Turing_machine) operate on an infinite tape, extending out to infinity in each direction. The tape is divided into cells, each of which can contain a symbol from a finite alphabet. The Turing machine consists of a finite state machine that moves along the tape, reading and writing symbols.

One way to generalise this simple definition is to alter the tape on which the Turing machine inhabits. Since there is only one possible one-dimensional tape, this involves moving into two dimensions. Natural choices for the grid are the square and hexagonal lattices; triangular and Penrose tilings are more exotic.

Another way to generalise the definition is to give the read-write head an orientation, so it moves either _forwards_ or does a _U-turn_ first. We're calling these machines _relative_, since their movement choices are relative to their current orientation. By contrast therefore the standard definition Turing machines are _absolute_.

The majority of this article is concerned with Turing machines on a square grid, both absolute and relative. Relative-movement 2D Turing machines are popularly known as [Turmites](http://en.wikipedia.org/wiki/Turmite).

## Background ##

Relative-movement Turing machines and 2D Turing machines have been investigated by many people over the years (both extensions are very obvious) but there are only a few papers:

  * Hartmanis, J. and Stearns, R. E. (1965) "On the Computational Complexity of Algorithms" Transactions of the American Mathematical Society, 117: 285-306.
> > Pascal Michel [tells us](http://www.logique.jussieu.fr/~michel/ha#2d) that this paper discusses 2D Turing machines. I haven't seen a copy myself.
  * [Brady, Allen H. (1995) "The Busy Beaver Game and the Meaning of Life". In: Herken, R. "The Universal Turing Machine: a half-century survey".](http://books.google.co.uk/books?id=YafIDVd1Z68C&lpg=PP1&ots=MZUbd8ijxj&dq=universal%20turing%20machine%20herken&pg=PA237#v=onepage&q=&f=false)
> > He considered "TurNing" machines (an independent invention of Turmites) and found 2-state 2-color machines that ran for 121 steps and printed 37 non-zero cells before halting. He did the same test on a triangular grid and found machines that took 171 steps and printed 39 non-zero cells before halting. He found a 3-state 2-color triangular grid machine that took 1721 steps and printed 351 non-zero cells before halting but the search was limited to 2,000 iterations.
  * Wolfram, S. (2002) "A New Kind of Science"
> > He has [a section on 2D Turing machines](http://www.wolframscience.com/nksonline/section-5.3).

## Make your own Turmites ##

**Absolute movement**

  * Run Scripts/Python/Rule-Generators/AbsoluteTurmite-gen.py in [Golly](http://golly.sourceforge.net). Copy-paste one of the absolute-movement specification strings, e.g.: `{{{1,'E',1},{1,'W',1}},{{1,'W',0},{1,'',0}}}`
  * Each machine is specified as a table of n\_states rows by n\_colors columns, written in (Western) reading order: the first row first, then then other rows.
  * Each triple is {A,B,C} where A is the new color to write: `[0,1,2,...,(n_colors-1)]`, B is the direction to move in (North, South, East, West) or empty to halt, C is the new state to adopt: `[0,1,2,...,(n_states-1)]`.
  * For example, the triple `{1,'S',3}` means: print a '1', move South, and adopt state 3.

**Relative movement**

  * Run Scripts/Python/Rule-Generators/Turmite-gen.py in [Golly](http://golly.sourceforge.net) and copy-paste one of the relative-movement specification strings below into the text box. E.g. `{{{1,2,0},{0,8,0}}}`
  * It uses a similar notation as the other script. The difference is in how the direction is specified: 1=forward, 2=right, 4=u-turn, 8=left, 0=halt. (This notation allows turmites to split, e.g. 10=turn left _and_ right.)
  * For example, the triple `{1,2,3}` means: print a '1', turn right (and move forward), and adopt state 3.

## Busy Beavers ##

This is a list of the best known [busy beavers](http://en.wikipedia.org/wiki/Busy_beaver). If you find improvements then overwrite the below.

### Summary ###

  1. Going from absolute movement to relative movement improves the score. The only exception found is Sigma\_relative(2,2)=4 which is the same as Sigma\_absolute(2,2).
  1. Going from 1D to 2D seems to improve the score other than for low numbers of state or colors.
  1. No examples are known where going from 2D to 3D improves the score but this is likely to be true for higher numbers of states and colors for the same reason that the 2D case outperforms the 1D case.

**Absolute movement**

| | <b>2-state</b> | <b>3-state</b> | <b>4-state</b> | <b>5-state</b> |
|:|:---------------|:---------------|:---------------|:---------------|
| <b>2-color</b> | 1D: 6 (4)<br>2D: 6 (4)<br>3D: 6 (4)<br>4D+?: 6 (4) <table><thead><th> 1D: 21 (6)<br>2D: 32 (11)<br>3D: 32 (11)<br>4D+: ? </th><th> 1D: 107 (13)<br>2D: 4,632 (244)<br>3D+: ? </th><th> 1D: 47,176,870 (4,098)<br>2D: 25,772,988,638 (935,508,401)<br>3D+: ? </th></thead><tbody>
<tr><td> <b>3-color</b> </td><td> 1D: 38 (9)<br>2D: 38 (10)<br>3D: 38 (10)<br>4D+: ? </td><td>  </td><td>  </td></tr>
<tr><td> <b>4-color</b> </td><td> 1D: 3,932,964 (2,050)<br>2D+: ? </td><td>  </td><td>  </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>2-state</b> </th><th> <b>3-state</b> </th><th> <b>4-state</b> </th></thead><tbody>
<tr><td> <b>2-color</b> </td><td> 1D: 13 (4)<br>2D: 121 (37)<br>3D: ? </td><td> 1D: 82 (9)<br>2D: 21,790 (2,793)<br>3D+: ? </td><td> 1D: 48,186 (96)<br>2D: 287,251 (19,875)<br>3D+: ? </td></tr>
<tr><td> <b>3-color</b> </td><td> 1D: 233 (19)<br>2D: 69,106 (5,060)<br>3D+: ? </td><td>  </td><td>  </td></tr>
<tr><td> <b>4-color</b> </td><td> 1D+: ? </td><td>  </td><td>  </td></tr></tbody></table>

Detailed results and credits are listed below.<br>
<br>
<h3>Searching for new champions</h3>

To find busy beavers you'll need a search program. Here's the one I was using to find some the results listed below: <a href='http://code.google.com/p/terminatingturmites/'>Terminating Turmites</a>

For other programs, the wikipedia page on busy beavers will guide you.<br>
<br>
<h3>Open Problems</h3>

<ul><li>What acceleration techniques can we find in 2D and higher? Heiner Marxen's macro machines can't obviously be used but can maybe be adapted?<br>
</li></ul><blockquote><a href='http://www.drb.insel.de/~heiner/BB/mabu90.html'>http://www.drb.insel.de/~heiner/BB/mabu90.html</a></blockquote>

<blockquote><a href='http://www.drb.insel.de/~heiner/BB/macro.html'>http://www.drb.insel.de/~heiner/BB/macro.html</a></blockquote>

<ul><li>So far no 3D or higher TM has been found that outperforms a 2D one with the same parameters. Do they exist or is 2D somehow special?</li></ul>

<ul><li>Can we understand anything about how BBs work or are they 'black boxes'? Some 1D machines (Surprise in a box) appear to have counting components - is there a similar mechanism in 2D?</li></ul>

<h3>2-state 2-color</h3>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 6<br><br><code>{{{1,'E',1},{1,'W',1}},{{1,'W',0},{1,'',1}}}</code> </td><td> 4<br><br>(same one) </td><td>  </td></tr>
<tr><td> <b>2D+</b> </td><td> (no improvement) </td><td> (no improvement) </td><td> In 3D there's no improvement either. And thinking about it, it will be true in all higher dimensions too - there are only 3 moves to be specified so if the 2D case is no improvement over the 1D case then adding further dimensions won't help either. Busy Beavers need to go over their own tracks to really be effective - and from this perspective it's really a surprise that some of the 2D cases outperform the 1D cases. TJH March 2010 </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 13<br><br><code>{{{1,4,1},{1,0,0}},{{1,1,0},{0,1,1}}}</code> </td><td> 4<br><br>(same one) </td><td> Allen H. Brady (in unpublished work) called these systems "Flippers" and discovered this Busy Beaver. </td></tr>
<tr><td> <b>2D</b> </td><td> 121<br><br><code>{{{1,8,0},{0,8,1}},{{1,0,0},{1,2,0}}}</code> </td><td> 37<br><br><code>{{{1,2,1},{1,1,0}},{{1,4,0},{1,0,0}}}</code> </td><td> Allen H. Brady's results from the paper. </td></tr>
<tr><td> <b>3D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<hr />

<h3>3-state 2-color</h3>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 21<br><br><code>{{{1,'E',1},{1,'',0}},{{1,'W',1},{0,'E',2}},{{1,'W',2},{1,'W',0}}}</code></td><td> 6<br><br><code>{{{1,'E',1},{1,'W',2}},{{1,'W',0},{1,'E',1}},{{1,'W',1},{1,'',0}}}</code> </td></tr>
<tr><td> <b>2D</b> </td><td> 32<br><br><code>{{{1,'S',1},{1,'W',2}},{{0,'W',2},{0,'E',1}},{{1,'N',0},{1,'',1}}}</code> </td><td> 11<br><br><code>{{{1,'W',2},{1,'E',1}},{{1,'S',0},{1,'N',1}},{{1,'N',1},{1,'',1}}}</code> </td><td> If better machines exist then they take more than 10,000 steps or move more than 100 squares from the starting position. TJH March 2010. </td></tr>
<tr><td> <b>3D</b> </td><td> (no improvement) </td><td> (no improvement) </td><td> If better machines exist then they take more than 1000 steps or move more than 50 squares from the starting position. TJH April 2010. </td></tr>
<tr><td> <b>4D+</b> </td><td> ? </td><td> ? </td><td> Unlikely to be any further improvement. </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 82<br><br><code>{{{1,1,1},{0,1,0}},{{1,4,0},{0,1,2}},{{1,1,0},{1,0,0}}}</code> </td><td> 9<br><br>(same one) </td><td> If better machines exist then they take more than 1,000 steps or move more than 50 squares from the starting position. Steps: TJH March 2010. Sigma: Allen H. Brady, unpublished. </td></tr>
<tr><td> <b>2D</b> </td><td> 21,790<br><br><code>{{{1,2,1},{1,1,0}},{{1,2,1},{1,2,2}},{{1,0,0},{1,1,0}}}</code><br><br><a href='http://ruletablerepository.googlecode.com/files/RBB32.PNG'>http://ruletablerepository.googlecode.com/files/RBB32.PNG</a> </td><td> 2,793<br><br>(same one) </td><td> If it is not the best, the best will take more than 200,000 steps or move more than 1,000 squares from the starting position. TJH March 2010. </td></tr>
<tr><td> <b>3D</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<hr />

<h3>2-state 3-color</h3>

Universal computation becomes possible for 1D Turing machines, as demonstrated by Alex Smith and Stephen Wolfram for <code>{{{1,'E',1},{2,'W',0},{1,'W',0}},{{2,'W',0},{2,'E',1},{0,'E',0}}}</code>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 38<br><br><code>{{{1,'E',1},{2,'W',1},{1,'',0}},{{2,'W',0},{2,'E',1},{1,'W',1}}}</code> </td><td> 9<br><br>(same one) </td></tr>
<tr><td> <b>2D</b> </td><td> (no improvement) </td><td> 10<br><br><code>{{{1,'N',1},{2,'W',1},{0,'E',0}},{{1,'S',0},{2,'N',1},{1,'',1}}}</code> </td><td> If better machines exist then they take more than 10,000 steps or move more than 100 squares from the starting position. TJH March 2010. </td></tr>
<tr><td> <b>3D</b> </td><td> (no improvement) </td><td> (no improvement) </td><td> If better machines exist then they take more than 500 steps or move more than 20 squares from the starting position. TJH April 2010. </td></tr>
<tr><td> <b>4D+</b> </td><td> ? </td><td> ? </td><td> Further improvement thought unlikely. </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 233<br><br><code>{{{1,4,1},{0,1,0},{2,1,0}},{{2,1,0},{1,0,0},{1,1,0}}}</code> </td><td> 19<br><br>(same one) </td><td> If better machines exist then they take more than 10,000 steps or move more than 100 squares from the starting position. TJH March 2010. </td></tr>
<tr><td> <b>2D</b> </td><td> 69,106<br><br><code>{{{1,2,0},{2,4,1},{2,1,0}},{{1,0,0},{2,2,0},{2,1,1}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/BB_rel_2s_3c_69106steps_5060cells.png' /> </td><td> 5,060<br><br>(same one)</td><td> If better machines exist then they take more than 200,000 steps or move more than 200 squares from the starting position. TJH April 2010. </td></tr>
<tr><td> <b>3D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<hr />

<h3>4-state 2-color</h3>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 107<br><br><code>{{{1,'E',1},{1,'W',1}},{{1,'W',0},{0,'W',2}},{{1,'',0},{1,'W',3}},{{1,'E',3},{0,'E',0}}}</code> </td><td> 13<br><br>(same one) </td></tr>
<tr><td> <b>2D</b> </td><td> 4,632<br><br><code>{{{1,'E',1},{0,'S',1}},{{1,'N',3},{1,'E',2}},{{0,'W',0},{1,'N',2}},{{1,'W',0},{0,'',0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/BB_abs_4s_2c_4632steps.png' /> </td><td> 244<br><br><code>{{{1,'E',1},{0,'W',0}},{{1,'W',3},{1,'S',0}},{{1,'S',0},{1,'',0}},{{1,'W',2},{1,'N',3}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/BB_abs_4s_2c_244nonzerocells.png' /> </td><td> If better machines exist then they take more than 100,000 steps or move more than 200 squares from the starting position. TJH March 2010. </td></tr>
<tr><td> <b>3D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 48,186<br><br><code>{{{1,4,1},{1,1,0}},{{1,1,2},{0,1,0}},{{1,4,3},{0,1,3}},{{0,0,0},{1,4,0}}}</code> </td><td> 96<br><br><code>{{{1,4,1},{1,1,0}},{{1,1,2},{0,1,0}},{{1,1,0},{1,1,3}},{{1,0,0},{0,1,0}}}</code> </td><td> Allen H. Brady, unpublished. That's a pretty amazing leap from 107 steps, 13 cells! </td></tr>
<tr><td> <b>2D</b> </td><td> 287,251<br><br><code>{{{1,1,1},{0,4,3}},{{0,2,0},{0,1,2}},{{1,0,0},{0,4,1}},{{1,1,0},{0,1,0}}}</code> </td><td> 19,875<br><br><code>{{{1,1,1},{1,0,0}},{{0,8,2},{0,8,2}},{{0,2,3},{1,4,0}},{{0,4,0},{0,1,0}}}</code> </td><td> These are not expected to be the final results. </td></tr>
<tr><td> <b>3D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<hr />

<h3>2-state 4-color</h3>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 3,932,964 </td><td> 2,050 </td></tr>
<tr><td> <b>2D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<b>Relative movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<hr />

<h3>5-state 2-color</h3>

<b>Absolute movement</b>

<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>1D</b> </td><td> 47,176,870 </td><td> 4,098 </td><td> Marxen and Buntrock. </td></tr>
<tr><td> <b>2D</b> </td><td> 25,772,988,638<br><br><code>{{{1,'N',1},{1,'',0}},{{1,'S',2},{0,'W',3}},{{0,'E',4},{0,'E',3}},{{1,'W',0},{0,'W',1}},{{0,'N',0},{0,'N',1}}}</code> </td><td> 935,508,401<br><br><code>{{{1,'N',1},{1,'',0}},{{0,'E',2},{1,'W',3}},{{1,'S',4},{0,'W',3}},{{1,'N',2},{1,'S',3}},{{1,'W',3},{0,'E',0}}}</code> </td><td> Georgi Gochev <geonwk@gmail.com>, Aug 2011. </td></tr></tbody></table>

<hr />

<h3>Beyond</h3>

For more states and colors, the Busy Beavers are enormous.<br>
<br>
For example, here are two example 3,3 Turing machines, neither of which are record holders:<br>
<br>
<code>{{{1,'N',1},{2,'S',2},{2,'S',1}},{{1,'W',2},{1,'N',1},{1,'',0}},{{1,'E',0},{0,'N',0},{0,'N',0}}}</code><br>
9304 steps.<br>
<code>{{{2,'W',1},{1,'',0},{2,'E',1}},{{2,'W',2},{0,'E',1},{2,'S',1}},{{1,'E',0},{0,'N',0},{0,'N',0}}}</code><br>
697 non-zero cells written.<br>
<br>
These are just examples - the actual record holders will have to be at least as large as the 1D case for which the record is <i><a href='http://www.cse.unr.edu/~al/BusyBeaver.html'>large</a></i>:<br>
<code>{{{1,'E',1},{2,'W',0},{1,'W',2}},{{0,'W',0},{2,'E',1},{1,'W',1}},{{1,'',0},{1,'E',0},{1,'E',2}}}</code><br>
(119,112,334,170,342,540 steps, 374,676,383 non-zero cells written)<br>
<br>
Here's the 3,3 1D machine described as <a href='http://www.cse.unr.edu/~al/busybeaversurprise.html'>Surprise-In-A-Box</a>:<br>
<code>{{{1,'E',1},{2,'W',1},{1,'W',2}},{{1,'W',0},{2,'E',1},{1,'E',1}},{{0,'',0},{2,'W',0},{0,'W',2}}}</code><br>

<hr />

<h3>Moore Turmites</h3>

On a square grid we could also consider turmites that move to a cell within its Moore neighborhood rather than its von Neumann neighborhood. Relative-movement Moore turmites would turn through multiples of 45 degrees.<br>
<br>
Note that hexagonal turmites (below) can be viewed as intermediate between von Neumann turmites and Moore turmites, the three cases having 4, 6 and 8 turns/moves to make, respectively.<br>
<br>
We haven't investigated Moore turmites yet.<br>
<br>
<hr />

<h3>Triangular Turmites</h3>

On a 2D grid of triangular cells, it doesn't make sense to talk about absolute-movement turmites because the triangles aren't all the same way up. Relative-movement turmites on a triangular grid were first studied by Allen H. Brady (ref at the top), and we've added some results of our own.<br>
<br>
Each triple is {A,B,C} where A is the new color to write: [0,n_colors), B is the direction to turn: {0=halt, 1=left, 2=right, 4=u-turn}, C is the new state to adopt: [0,n_states). For example, the triple <code>{1,2,3}</code> means: print a '1', turn right, and adopt state 3.<br>
<br>
<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>2-state 2-color</b> </td><td> 171<br><br><code>{{{1,2,1},{1,0,0}},{{0,1,1},{1,4,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite2s2c_171steps_27cells.png' /> </td><td> 39<br><br><code>{{{1,2,0},{0,2,1}},{{1,0,0},{1,1,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite2s2c_134steps_39cells.png' /> </td><td> Allen H. Brady's results from the paper, confirmed. If better machines exist then they take more than 100,000 steps or move more than 1,000 squares from the starting position. </td></tr>
<tr><td> <b>3-state 2-color</b> </td><td> 4,499<br><br><code>{{{1,2,1},{0,1,1}},{{1,1,2},{1,2,0}},{{0,4,1},{1,0,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite3s2c_4499steps_298cells.png' /> </td><td> 1,611<br><br><code>{{{1,2,1},{1,2,0}},{{1,1,1},{1,1,2}},{{1,0,0},{0,1,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite3s2c_3633steps_1611cells.png' /> </td><td> If better machines exist then they take more than 100,000 steps or move more than 200 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>2-state 3-color</b> </td><td> 19,829<br><br><code>{{{1,2,1},{2,2,1},{1,0,0}},{{1,2,0},{0,1,1},{0,1,1}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite2s3c_19829steps_635cells.png' /> </td><td> 1,015<br><br><code>{{{1,2,1},{0,2,0},{1,4,1}},{{2,2,0},{1,0,0},{0,1,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/TriTurmite2s3c_4653steps_1015cells.png' /> </td><td> If better machines exist then they take more than 100,000 steps or move more than 200 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

Golly 2.2 has a script <code>TriTurmite-gen.py</code> for generating CA for these turmites.<br>
<hr />

<h3>Hexagonal Turmites</h3>

<b>Absolute movement</b>

Here there are 6 directions for the turmites to move in: 'A', 'B', 'C', 'D', 'E', 'F'. Golly 2.2 has a script <code>AbsoluteHexTurmite-gen.py</code> for generating CA for these turmites.<br>
<br>
<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>2-state 2-color</b> </td><td> 6<br><br><code>{{{1,'A',1},{1,'B',1}},{{1,'D',0},{1,'',0}}}</code> </td><td> 4<br><br>(same one) </td><td> If better machines exist then they take more than 100,000 steps or move more than 100 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>3-state 2-color</b> </td><td> 33<br><br><code>{{{1,'A',1},{1,'',0}},{{1,'E',2},{0,'A',2}},{{1,'C',1},{1,'D',0}}}</code> </td><td> 13<br><br><code>{{{1,'A',1},{1,'C',2}},{{1,'E',2},{1,'B',0}},{{1,'D',0},{1,'',0}}}</code> </td><td> If better machines exist then they take more than 100,000 steps or move more than 20 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>2-state 3-color</b> </td><td> 38<br><br><code>{{{1,'A',1},{2,'D',1},{1,'',0}},{{2,'D',0},{2,'A',1},{1,'D',1}}}</code> </td><td> 14<br><br><code>{{{1,'A',1},{2,'C',1},{1,'',0}},{{2,'D',0},{2,'B',0},{1,'E',0}}}</code> </td><td> If better machines exist then they take more than 100,000 steps or move more than 20 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>4-state 2-color</b> </td><td> 1351<br><br><code>(spec string lost)</code>  </td><td> 165<br><br><code>{{{1,'A',1},{1,'',0}},{{1,'B',2},{0,'E',3}},{{1,'A',3},{1,'C',1}},{{1,'D',1},{1,'B',0}}}</code> </td><td> Preliminary results (9% explored) - not yet beating the square-grid case. TJH June 2010. </td></tr>
<tr><td> <b>+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

Note that absolute-movement hexagonal-celled Turing machines can simulate any square grid machine, so their scores can never be lower. But their improvements (where there are any) are surprisingly small in the cases examined.<br>
<br>
<b>Relative movement</b>

Extending our convention: 0=halt, 1=no turn, 2=left, 4=right, 8=back-left, 16=back-right, 32=u-turn. Golly 2.2 has a script <code>HexTurmite-gen.py</code> for generating CA for these turmites.<br>
<br>
<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>2-state 2-color</b> </td><td> 54<br><br><code>{{{1,16,1},{1,0,0}},{{1,16,0},{1,1,1}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/HexTurmite2s2c_54steps_24cells.png' /> </td><td> 24<br><br>(same one) </td><td> If better machines exist then they take more than 100,000 steps or move more than 50 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>3-state 2-color</b> </td><td> 57,867<br><br><code>{{{1,16,0},{1,8,1}},{{1,8,2},{1,16,0}},{{1,0,0},{0,1,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/HexTurmite3s2c_57867steps_1654cells.png' /> </td><td> 1,654<br><br>(same one) </td><td> If better machines exist then they take more than 500,000 steps or move more than 50 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>2-state 3-color</b> </td><td> 44,438<br><br><code>{{{0,16,1},{2,16,1},{1,0,0}},{{1,1,0},{1,8,1},{1,1,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/HexTurmite2s3c_44438steps_1731cells.png' /> </td><td> 2,893<br><br><code>{{{1,16,1},{1,1,0},{1,8,0}},{{1,16,0},{2,8,0},{1,0,0}}}</code><br><br><img src='http://ruletablerepository.googlecode.com/files/HexTurmite2s3c_17020steps_2893cells.png' /> </td><td>  If better machines exist then they take more than 500,000 steps or move more than 50 squares from the starting position. TJH May 2010. </td></tr>
<tr><td> <b>+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

The 2-state 2-color results (54, 24) are significantly smaller than the square-grid (121, 37) and triangular-grid (171, 39) results, which is perhaps surprising since there are more ways for the turmites to turn (6 as opposed to 4 or 3). But then again they can only make 3 turns so maybe it's like the 3D case (above) - they don't have enough moves to take advantage of the grid. But the 3-state 2-color steps result (S=57,867) is far ahead of the square-grid (S=21,790) and triangular-grid result (S=4,499).<br>
<br>
<hr />

<h3>Penrose turmites</h3>

Turmites on Penrose tilings are especially interesting. Due to the aperiodicity of the tiling, an infinite amount of information can be stored in the initial location of the Turmite. This means that it is possible to engineer a Universal Turmite, where the program is encoded entirely in its initial position, and not in the initial contents of the tape.<br>
<br>
However, since the time to halt depends on the position of the Turmite, there is no analogue of the Busy Beaver problem; with a sufficient number of states, a Turmite could take arbitrarily long to halt.<br>
<br>
<hr />

<h3>Extinction turmites</h3>

<a href='http://en.wikipedia.org/wiki/Ed_Pegg,_Jr.'>Ed Pegg, Jr.</a> <a href='http://www.mathpuzzle.com/26Mar03.html'>extended</a> the turmite idea by allowing turmites to turn <i>both</i> left and right, for example. When turmites collide they annihilate each other. Another form of the busy beaver game is therefore to find turmites that go extinct after writing the most non-zero cells or taking the most steps.<br>
<br>
<b>Relative movement, square grid</b>

These turmites take advantage of the notation 1=forward, 4=u-turn, 2=right, 8=left, 0=halt. To turn in two or more directions, simply add the values together. E.g. 10=turn left and right.<br>
<br>
<table><thead><th> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <b>2-state 2-color</b> </td><td> 12<br><br><code>{{{1, 8, 0}, {1, 2, 1}}, {{1, 10, 0}, {1, 8, 1}}}</code> </td><td> 10<br><br>(same one) </td><td> Discovered by Ed Pegg, Jr. </td></tr>
<tr><td> <b>3-state 3-color</b> </td><td> 204<br><br><code>{{{1, 2, 0}, {2, 8, 2}, {2, 1, 1}}, {{1, 1, 2}, {1, 1, 1}, {1, 8, 1}}, {{2, 10, 0}, {2, 8, 1}, {2, 8, 2}}}</code> </td><td> 256<br><br>(same one) </td><td> Discovered by Ed Pegg, Jr. </td></tr>
<tr><td> <b>+</b> </td><td> ? </td><td> ? </td></tr></tbody></table>

<b>Absolute movement, 1D, 3D+, triangular grid, hexagonal grid...</b>

No-one has investigated extinction turmites on these cases, so there's lots left to be discovered.<br>
<br>
<hr />

<h3>Non-halting Busy Beavers</h3>

(Asked by Ed Pegg, Jr.)<br>
<br>
If we consider turmites <i>without</i> a halting state then there is still an interesting question:<br>
<ul><li>What turmite runs the longest before becoming predictable?</li></ul>

Results collected at EdPeggsBusyBeaverTurmiteChallenge. Let us know what you find.<br>
<br>
As far as we know these are the current record holders:<br>
<br>
<b>1-state 2-color relative movement:</b><br>
<code>{{{1,2,0},{0,8,0}}}</code><br>
Langton's Ant: 9,977 steps before making a highway.<br>
<br>
<b>2-state 2-color relative movement:</b><br>
<code>{{{1,2,1},{0,8,1}},{{1,8,1},{0,1,0}}} </code> <br> 8,362,028,000 (+1000) steps before making a highway. (Mark Jeronimus) This rule is a slightly modified version of a rule by Georgi Gochev.<br>
<a href='http://ruletablerepository.googlecode.com/files/t22r121081181010.png'><img src='http://ruletablerepository.googlecode.com/files/t22r121081181010_small.png' /></a>

<b>3-state 2-color absolute movement:</b><br>
<code>{{{0,'S',1},{1,'W',1}},{{1,'E',2},{1,'S',2}},{{1,'W',0},{0,'N',0}}}</code> <br>
("Perfectionist": 15.5 million timesteps before making a highway)<br>
<br>
<hr />

<h2>Searching for high entropy patterns</h2>

Wolfram says this of 2D Turing machines:<br>
<br>
<blockquote><i>"For Turing machines with two or three possible states, only repetitive and nested behavior normally seem to occur. With four states, more complex behavior is possible, but it is still rather rare."</i> <a href='http://www.wolframscience.com/nksonline/page-184'>(NKS, p.184)</a></blockquote>

However there <i>are</i> examples of complex 3-state 2-color 2D Turing machines. These below were located by a program searching for patterns with high <a href='http://en.wikipedia.org/wiki/Entropy_%28information_theory%29'>entropy</a>:<br>
<br>
<br>
This pattern is seemingly random for 15.5 million timesteps, before making a repetitive highway:<br>
<br>
<code>{{{0,'S',1},{1,'W',1}},{{1,'E',2},{1,'S',2}},{{1,'W',0},{0,'N',0}}}</code><br> (Patterns/Turmites/Perfectionist.rle in Golly)<br>
<br>
<br>
<br>
This pattern expands at a logarithmic rate, and behaves quite unusually:<br>
<br>
<code>{{{0,'N',2},{1,'S',1}},{{0,'E',0},{0,'S',0}},{{1,'W',1},{1,'N',2}}}</code><br>

This pattern grows extremely slowly, so is perhaps doing some form of counting, but appears random. Here's an animation of the states progressing from 1E9 timesteps up to 100E9 timesteps (100 frames, each 1 billion timesteps):<br>

<img src='http://ruletablerepository.googlecode.com/files/AlienCounter.gif' />

This resembles a form of binary counter. However, it is not performing traditional binary counting, as long strings of '1' symbols are replaced with alternating '1's and '0's, instead of solid '0's. If the counter didn't produce extra lines, and just worked in one dimension, it would count like so:<br>
<br>
<pre><code><br>
1<br>
01<br>
11<br>
101<br>
011<br>
111<br>
0101<br>
1101<br>
1011<br>
0111<br>
1111<br>
10101<br>
01101<br>
11101<br>
01011<br>
11011<br>
10111<br>
01111<br>
11111<br>
010101<br>
<br>
</code></pre>

Notice that there is 1 one-digit number, 2 two-digit numbers, 3 three-digit numbers, 5 four-digit numbers and 8 five-digit numbers. These correspond to the Fibonacci numbers, which means that it effectively counts in base-phi, where phi is the golden number. This is quite unexpected, as phi is an irrational number, so doesn't usually occur as the base for discrete counting.<br>
<br>
However, occasionally a parallel side-branch is created. This makes the counting process less regular, as the branches interfere with each other.<br>
<br>
<br>
<br>
<h2>The examples in Wolfram's A New Kind of Science</h2>

3-state 2-color 2D Turing machine from NKOS <a href='http://www.wolframscience.com/nksonline/page-184'>p184</a>:<br>
states: 0=north, 1=SE, 2=SW<br>
colors: 0=white, 1=grey<br>
<code>{{{1,'E',2},{0,'E',1}},{{1,'W',0},{1,'N',1}},{{0,'S',1},{1,'N',0}}}</code>

Five 4-state 2-color 2D Turing machines from NKOS <a href='http://www.wolframscience.com/nksonline/page-185'>p185</a>:<br>
states: 0=north, 1=east, 2=south, 3=west<br>
colors: 0=white, 1=grey<br>
(a): <code>{{{1,'S',1},{0,'W',2}},{{1,'S',2},{1,'E',1}},{{1,'N',3},{0,'S',0}},{{0,'E',1},{0,'N',0}}}</code><br>
(b): <code>{{{1,'E',3},{0,'N',0}},{{1,'W',2},{1,'S',1}},{{0,'N',0},{1,'S',1}},{{1,'E',1},{0,'S',0}}}</code><br>
(c): <code>{{{1,'W',1},{0,'E',2}},{{0,'E',3},{1,'W',0}},{{0,'N',0},{0,'S',3}},{{1,'S',0},{1,'N',1}}}</code><br>
(d): <code>{{{0,'E',3},{0,'W',1}},{{1,'N',0},{1,'N',3}},{{0,'W',1},{1,'S',2}},{{1,'S',2},{0,'E',1}}}</code><br>
(e): <code>{{{1,'N',1},{0,'S',1}},{{1,'S',3},{0,'N',2}},{{1,'W',0},{1,'N',1}},{{1,'S',2},{0,'E',1}}}</code>

Wolfram devotes <a href='http://www.wolframscience.com/nksonline/page-186'>a page</a> to example (e)<br>
and <a href='http://www.wolframscience.com/nksonline/page-184'>describes it</a> as: "one example where the behavior seems in many respects completely random." In fact, as I reported <a href='http://forum.wolframscience.com/showthread.php?s=86e914a0e833e3ad447abfd576c8d0a8&threadid=1749'>here</a> the pattern is periodic, with period 2,074,575 and dx=3953, dy=1912.<br>
<br>
3-state 2-color 2D Turing machine from NKOS Notes, <a href='http://www.wolframscience.com/nksonline/page-931'>p931</a>:<br>
states: 0=north, 1=SE, 2=SW<br>
colors: 0=white, 1=grey<br>
<code>{{{1,'N',2},{1,'W',0}},{{0,'W',0},{1,'S',0}},{{1,'S',1},{0,'E',1}}}</code>

<h2>Other halting machines found by Georgi Gochev</h2>
<table><thead><th> <b>Machine</b> </th><th> <b>S (steps)</b> </th><th> <b>Sigma (non-zero cells left)</b> </th></thead><tbody>
<tr><td> <code>{{{1,'N',1},{1,'',0}},{{1,'E',2},{1,'E',3}},{{1,'W',3},{0,'S',4}},{{0,'W',4},{1,'S',3}},{{1,'E',0},{0,'W',4}}}</code> </td><td> 12,135,580,977 </td><td> 319,966 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',1}},{{0,'E',2},{1,'W',3}},{{1,'S',4},{0,'W',3}},{{1,'N',2},{1,'S',3}},{{1,'W',3},{0,'E',0}}}</code> </td><td> 7,131,195,542 </td><td> 935,508,401 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',1}},{{1,'E',2},{1,'N',1}},{{1,'W',3},{0,'E',1}},{{1,'S',0},{1,'S',4}},{{1,'W',2},{0,'E',1}}}</code> </td><td> 1,894,226,289 </td><td> 581,857,738 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'N',4}},{{1,'S',2},{1,'',1}},{{1,'S',4},{1,'S',3}},{{0,'E',2},{0,'W',0}},{{1,'N',0},{0,'S',2}}}</code> </td><td> 1,635,991,442 </td><td> 166,125,459 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',1}},{{1,'S',2},{0,'W',3}},{{1,'W',4},{0,'E',3}},{{1,'S',2},{1,'N',3}},{{1,'N',0},{0,'S',3}}}</code> </td><td> 1,547,228,624 </td><td> 341,883,343 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'E',3}},{{1,'E',2},{1,'',1}},{{1,'W',3},{1,'N',3}},{{0,'S',0},{0,'W',4}},{{0,'S',3},{0,'N',1}}}</code> </td><td> 1,366,930,758 </td><td> 855,482 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',1}},{{1,'E',2},{1,'W',1}},{{0,'N',3},{1,'W',4}},{{1,'W',1},{0,'N',4}},{{1,'N',0},{0,'S',1}}}</code> </td><td> 1,187,246,809 </td><td> 668,652 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',1}},{{1,'S',2},{1,'W',1}},{{1,'N',3},{0,'S',1}},{{0,'N',0},{1,'E',4}},{{1,'N',2},{0,'S',1}}}</code> </td><td> 1,047,936,297 </td><td> 314,986,440 </td></tr>
<tr><td> <code>{{{1,'N',1},{1,'',0}},{{0,'S',2},{0,'E',4}},{{0,'W',3},{1,'E',1}},{{1,'W',0},{1,'W',3}},{{0,'W',0},{0,'E',2}}}</code> </td><td> 1,918,870 </td><td> 66 </td></tr></tbody></table>

