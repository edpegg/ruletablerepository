

&lt;html&gt;




&lt;title&gt;

The Rule Table Repository

&lt;/title&gt;




&lt;body&gt;



<p>
Please visit the<br>
<a href='http://code.google.com/p/ruletablerepository/'>Rule Table Repository</a>
web site for more information. In particular, see<br>
<a href='http://code.google.com/p/ruletablerepository/wiki/TheRules'>TheRules</a>
page for more details about the rules listed below, including some nice images.<br>
</p>

<p>
NOTE: Links flagged by "**" will load rules and patterns already included in the<br>
latest version of Golly. The other links will download external rules<br>
and patterns not supplied with Golly.<br>
</p>**

<p>Contents:<br>
<dd><a href='#jvn'><b>Von Neumann's CA and close variations</b></a></dd>
<dd><a href='#codd'><b>Codd's CA and descendents</b></a></dd>
<dd><a href='#loops'><b>Self-replicating loops</b></a></dd>
<dd><a href='#wireworld'><b>WireWorld and derivatives</b></a></dd>
<dd><a href='#comp'><b>Other computation rules</b></a></dd>
<dd><a href='#gases'><b>Lattice gases</b></a></dd>
<dd><a href='#margolus'><b>Margolus neighborhood</b></a></dd>
<dd><a href='#hexagonal'><b>Hexagonal neighborhood</b></a></dd>
<dd><a href='#triangular'><b>Triangular neighborhood</b></a></dd>
<dd><a href='#turing'><b>Langton's Ant and other Turing Machines</b></a></dd>
<dd><a href='#life'><b>Life-inspired CAs</b></a></dd>
<dd><a href='#misc'><b>Miscellaneous</b></a></dd>
</p>

<a></a>
<h1>Von Neumann's CA and close variations</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:JvN29'>JvN29</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
John von Neumann's original 29-state CA.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Nobili32'>Nobili32</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Renato Nobili's extension of von Neumann's 29-state CA to allow easier crossing of wires,<br>
leading to simpler machines.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Hutton32'>Hutton32</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
This is a modification of Nobili32 by Tim Hutton, to allow simpler construction and<br>
rotational invariance.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Codd's CA and descendents</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:Codd'>Codd</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Edgar F. Codd reduced von Neumann's CA to 8 states.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Codd-ICRA.zip'>Codd-ICRA</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A team of Hungarian researchers modified Codd's rules so that crossovers can be made with<br>
only nine cells, and gates can be constructed by passing 7-0 signals.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Devore'>Devore</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
John Devore altered Codd's rule to allow for more compact machines.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Codd2'>Codd2</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Tim Hutton realised that Codd's rule table required three extra transitions in order<br>
to be able to sheath large complex structures.<br>
With this rule, an implementation of Codd's self-replicating machine was created:<br>
<a href='get:http://ruletablerepository.googlecode.com/files/Codd-self-rep.zip'>Codd-self-rep.zip (12MB)</a>.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Self-replicating loops</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:Langtons-Loops'>Langtons-Loops</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Chris G. Langton extended Codd's rules to allow a novel form of simple<br>
self-replicator - the loop.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Byl-Loop'>Byl-Loop</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
J. Byl reduced the size of Langton's Loop.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Chou-Reggia-1'>Chou-Reggia-1</a><a href='rule:Chou-Reggia-2'>Chou-Reggia-2</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A further reduction of Langton's Loops - down to just five cells.<br>
This is a modification of Byl's loop that doesn't need a sheath.<br>
However, the simplicity of it makes it difficult to identify as a loop.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Tempesti'>Tempesti</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Gianluca Tempesti is a programmable loop that can construct inside itself.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Perrier'>Perrier</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Perrier added universal computation capabilities to Langton's loop by adding<br>
a program stack and an extensible data tape.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:SDSR-Loop'>SDSR-Loop</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Hiroki Sayama introduced a change to Langton's Loops that caused dead loops<br>
to disappear, allowing live ones to reproduce further.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Evoloop'>Evoloop</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Another loop from Sayama, that allows colliding loops to sometimes merge genetic content.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/SexyLoop.zip'>Sexyloop</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Nicolas Oros and Chrystopher L. Nehaniv modified Sayama's evoloop to allow the transfer of genetic material<br>
from one loop into another. The zip file contains 3 rule tables (Sexyloop-M1, Sexyloop-M2, F-sexyloop)<br>
and some example patterns. Details and references can be found<br>
<a href='http://www.socsci.uci.edu/~noros/sexyloop.html'>here</a>.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/GoucherLoops.zip'>Goucher's Loops</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 24-state version of Langton's loops, that permits construction and computation universality,<br>
both left and right turns, genome combination and competition.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Bakker-Loop.zip'>Bakker loop</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Grant Bakker made a 7-state sheath-free loop with the interesting property of sending out 'runners'<br>
to start new colonies. His Java implementation is included in the zip.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/svn/trunk/downloads/Petelka.zip'>Petelka</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Petelka (Pętelka - "Little loop" in Polish) with variant Petelka-2 - rule with something similar to little loop. Probably it is not a loop beating the record of Chou-Reggia Loop, but I don't know which part of definition is not fulfilled. Petelka has also 1D replicator. In Petelka-2 the same pattern creates two loops.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>WireWorld and derivatives</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:WireWorld'>WireWorld</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Brian Silverman's famous CA for electronic wiring.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/WWEJ3.zip'>WWEJ3</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
See <a href='http://code.google.com/p/ruletablerepository/wiki/TheRules'>TheRules</a> for old WWE rules.<br>
WWEJ3 by Mark Jeronimus and Alan Tennant, coded by Mark Jeronimus, contains all the functionality of<br>
old WWEs with none of the compromises or bugs, and with only 17 states.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/WireWorldMarked.zip'>WireWorldMarked</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A marked version of WireWorld. It supports six extra wire colors but no extra functionality.<br>
A marked version of the Quinapalus' Primes Computer is included.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/switch.zip'>WSwitch</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 5-state rule by Alan Tennant where the construction of logic gates is impossible.<br>
Instead several types of pulse divider are possible.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/particles.zip'>Particles</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Particles is loosely based on Wireworld, with a few differences:<br>
Particles move through open space instead of wires, and they can also collide to create, move, or remove blocks.<br>
This means that a Particles system could reproduce itself. A rule by Joel Walker.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Blocks_and_Walls_wconradwalden.zip'>Blocks And Walls</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A complex yet simple to use cellular automata that is based loosely off Particles.<br>
A rule by Conrad Walden.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Other computation rules</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:Banks-I'>Banks-I</a><a href='rule:Banks-II'>Banks-II</a><a href='rule:Banks-III'>Banks-III</a><a href='rule:Banks-IV'>Banks-IV</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Edwin Roger Banks made CA's that support universal computation and construction,<br>
using fewer states than before.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/svn/trunk/downloads/Serizawa1.1.zip'>Serizawa</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 3-state von Neumann neighborhood rule capable of universal computation and construction. A quadratic self-replicator has not yet been implemented in this rule, but the latest archive includes Michael Simkin's linear self-constructing Geminoid puffer.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/MinskyCA.zip'>MRM</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 4-state rule made by Paul Chapman to support Minsky Register Machines, up to and<br>
including universal MRMs.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Lattice gases</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:HPP'>HPP</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
The HPP lattice gas can be simulated in the Margolus rule, but Brian Wylie showed<br>
how to simulate it with 16 states and the von Neumann neighborhood.<br>
Tim Hutton added another 16 'reflection' states to allow the rule to function<br>
in a bounded, non-toroidal space.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/DLA.zip'>DLA</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Diffusion-limited aggregation using the HPP lattice gas. This model was studied<br>
to simulate the fractal growth characterised by electrolysis of copper sulphate.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Pressure.zip'>Pressure</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Pressure is a rule by Dean Hickerson, which is loosely based on gas particles<br>
exerting pressure on the walls of a chamber.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Margolus neighborhood</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<!-- Margolus neighborhood is not currently supported by Golly<br>
<blockquote><a href='rule:DLA-Margolus'>DLA-Margolus</a><b>--><br></b><a href='rule:DLA-Margolus-emulated'>DLA-Margolus-emulated</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Diffusion-limited aggegation in the Margolus neighborhood.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<!-- Margolus neighborhood is not currently supported by Golly<br>
<a href='rule:BBM-Margolus'>BBM-Margolus</a><b>--><br></b><a href='rule:BBM-Margolus-emulated'>BBM-Margolus-emulated</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Ed Fredkin's Billiard Ball Model in the Margolus neighborhood.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<!-- Margolus neighborhood is not currently supported by Golly<br>
<a href='rule:Sand-Margolus'>Sand-Margolus</a><b>--><br></b><a href='rule:Sand-Margolus-emulated'>Sand-Margolus-emulated</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
MCell's 'Sand' rule in the Margolus neighborhood.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Hexagonal neighborhood</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='get:http://ruletablerepository.googlecode.com/files/Hex-B2omS2.zip'>Hex-B2omS2</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 2-state non-totalistic CA on a hexagonal grid, by Ken Preston Jr.<br>
This rule was first described in<br>
<a href='http://www.conwaylife.com/wiki/index.php?title=Lifeline_Volume_2'>LifeLine number 2</a>
on page 15. The rule name uses Paul Callahan's notation (see below).<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Snowflake.zip'>Snowflake</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Contains a script for generating examples of Norman Packard's snowflake-like CA, described in<br>
<a href='http://www.scipress.org/e-library/sof/pdf/0095.PDF'>this 1986 paper</a>.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Hex-B2oS2m34.zip'>Hex-B2oS2m34</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 2-state non-totalistic CA on a hexagonal grid, by Paul Callahan.<br>
See Paul's excellent <a href='http://www.radicaleye.com/lifepage/hexrule.txt'>article</a>
describing the notation used in the rule name, and the many interesting objects he discovered<br>
(some are included in the zip file).<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/HexBuss.zip'>HexBuss</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A 3-state totalistic CA on a hexagonal grid, by Frank Buss. See Frank's<br>
<a href='http://www.frank-buss.de/automaton/hexautomaton.html'>website</a> for more details.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Triangular neighborhood</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='get:http://ruletablerepository.googlecode.com/files/TriLife.zip'>TriLife</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
2-state totalistic CA rules on a triangular grid are emulated by a 4-state CA.<br>
Based on the work by Carter Bays (see this <a href='http://www.cse.sc.edu/~bays/trilife3/home.html'>applet</a>).<br>
The zip file includes a script for generating TriLife-Bnnn...Snnn... rules, some example rules and patterns,<br>
and another script that counts the number of triangles in a TriLife pattern.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Langton's Ant and other Turing Machines</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:Langtons-Ant'>Langtons-Ant</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Langton's other famous system. An ant moves around an infinite universe, flipping<br>
the color of the squares it lands on and turning left or right accordingly.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Langtons-Ant-nColor.zip'>n-color extension of Langton's Ant</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A script for creating examples in the n-color extension of Langton's Ant.<br>
See the <a href='http://www.youtube.com/watch?v=1X-gtr4pEBU'>YouTube video</a>.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Langtons-Ant-Count.zip'>Langtons-Ant-Count</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Langton's Ant can be modified to count in binary, as shown in this<br>
<a href='http://mathworld.wolfram.com/Turmite.html'>MathWorld article</a>.<br>
It is a special case of a Turmite, or 2-dimensional isotropic Turing machine. It only differs from Langton's Ant<br>
in that it moves forwards on a white square, rather than turning left.<br>
This 'counting ant' was discovered by Ed Pegg, Jr.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Turmites.zip'>Turmites</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A <a href='http://en.wikipedia.org/wiki/Turmite'>Turmite</a> is a 2D Turing machine;<br>
a generalization of Langton's Ant to n states and m colors.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/AbsoluteTurmites.zip'>Absolute Turmites</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
While turmites store their orientation as part of their state, absolute turmites have no orientation.<br>
Fewer interesting examples are known. Included are some examples from<br>
<a href='http://wolframscience.com'>Wolfram's NKS</a>
including one recently discovered to be periodic.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Iceskater.zip'>Iceskater</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A rule by Jordan Goldstein.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:Worm-1040512'>Worm-1040512</a><a href='rule:Worm-1042015'>Worm-1042015</a><a href='rule:Worm-1042020'>Worm-1042020</a><a href='rule:Worm-1252121'>Worm-1252121</a><a href='rule:Worm-1525115'>Worm-1525115</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Dean Hickerson's implementation of Paterson's Worms. The hexagonal neighborhood<br>
is emulated in the Moore neighborhood.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/BusyBeaver.zip'>BusyBeaver</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Adam P. Goucher has made a program to convert m-state n-symbol Turing machines into rule tables.<br>
The two example machines are Busy Beavers, Turing machines that try to write as many<br>
'1's as possible before halting. To run each machine in Golly, seed the universe with<br>
a single cell of state 2.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Turing-wolfram.zip'>Turing-wolfram</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
This rule simulates Wolfram's 2-state 3-symbol Turing Machine, which was proven by Alex Smith<br>
to be universal. The rule displays all previous states of the machine instead of just the current one.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Life-inspired CAs</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='get:http://ruletablerepository.googlecode.com/files/LifeColor_FrancoisBoisson.zip'>LifeColor</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A colored variant of the Game of Life, by Francois Boisson.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:LifeOnTheEdge'>LifeOnTheEdge</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Franklin T. Adams-Watters described a CA in which all the action occurs on the<br>
edges of a square grid. Each edge can be on or off and has six neighbors, three at each end.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='rule:LifeOnTheSlope'>LifeOnTheSlope</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
An implementation of the above rule, rotated 45 degrees so that only 2 live states are required.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/LifeHistoryRules.zip'>HistoricalLife</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Includes an implementation of the classic game of life that highlights the cells<br>
that were ever alive by Dave Greene, translated to a table by Calcyman and a five-state<br>
extension of the HistoricalLife rule originally by Brice Due.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/simulators.zip'>Life Pattern Emulators</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Two rules, "Clouds" by Dean Hickerson and "Primes" by Adam P. Goucher, designed to simulate<br>
two of Dean's transcendental Life patterns. Included in the zip file are the rule tables,<br>
sample patterns and equivalent Life patterns.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/extendedlife.zip'>ExtendedLife</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Conway's Game of Life with a few extra special states.<br>
Idea and rule table by Martin Grant, a.k.a. "Extrementhusiast".<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/MilhinSA.zip'>MilhinSA</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
3 states, similar to Conway's Game of Life, by Milkhin Sergei.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/SlowLife.zip'>SlowLife</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A variant of Life that shows births (green cells) and deaths (red cells) in every 2nd generation.<br>
SlowLife patterns work the same as in Life, but twice as slow.<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>

<a></a>
<h1>Miscellaneous</h1>

<p>
<table cellpadding='4' border='0' cellspacing='0' width='100%'>
<tr><td width='20%'><b>
<blockquote><a href='rule:Ed-rep'>Ed-rep</a><b></b></td></b><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
In 1970, Terry Winograd proved that Fredkin's replicator CA (the parity rule B1357/S1357)<br>
could be extended to N states, as long as N is a prime number.<br>
Contains a 7-color photo of Ed Fredkin that replicates.<br>
<a href='open:Patterns/Other-Rules/Ed-rep.rle'>Ed-rep.rle</a><b></td></tr></table></td></tr></b><tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Sandpile.zip'>Sandpile</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A simple 2D model of a sandpile was found to self-organize itself to criticality.<br>
<a href='http://en.wikipedia.org/wiki/Bak%E2%80%93Tang%E2%80%93Wiesenfeld_sandpile'>Wikipedia</a>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/CyclicCA.zip'>CyclicCA</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A rule investigated by David Griffeath. This rule is a very basic CA that shows<br>
competition emerging from a random initial seed.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/JustFriends.zip'>JustFriends</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A non-totalistic 2D binary rule by David Bell.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/PhotonXor.zip'>PhotonXor</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
David Eppstein discovered this one-dimensional system whilst experimenting with the rule B25/S4.<br>
It exhibits pseudo-random walks, and can be simulated in O(n log n) time using an algorithm by Tomas Rokicki.<br>
By interpreting its walk in binary, it can be used as an (aperiodic) pseudo-random number generator &mdash;<br>
see <a href='http://yucs.org/~gnivasch/life/photonXOR/index.html'>Gabriel Nivasch's web page</a>.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/TrickyBees.zip'>TrickyBees</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A chaotic rule by Alan Tennant where each state becomes progressively more inert<br>
in which patterns are surprisingly tricky to construct.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/MazeSolver.zip'>MazeSolver</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
MazeSolver is a 13-state rule that solves any maze, using a flood fill method to locate the exit, before<br>
backtracking to the start to highlight the shortest possible route. MazeSolver2 is an extended version<br>
that uses the Moore neighborhood to allow diagonal filling and backtracking. The zip file contains the<br>
necessary tables, icons and colors, as well as example patterns and scripts for creating random mazes.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/CollatzConjecture.zip'>3n+1</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Dean Hickerson created this rule table for determining the number of iterations required for each<br>
positive integer to reach 1 in the<br>
<a href='http://en.wikipedia.org/wiki/Collatz_conjecture'>Collatz conjecture</a>
(also known as the "3n+1" conjecture).<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/RepRoller.zip'>RepRoller</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A simple way of allowing any pattern to be replicated and triggered.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Wave.zip'>Wave</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A cellular automaton by Keiji and metacell implemented within this rule.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/reversible_rule_paul.zip'>ReversibleLife</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Paul Nasca's ReversibleLife rule, made using the second-order technique.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Squaredance.zip'>Squaredance</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Squaredance is a rule by Dean Hickerson in which rectangles grow and shrink pseudorandomly.<br>
For more details, see readme.txt in the zip file.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Sand.zip'>Sand</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Sand is a rule by Andrew Trevorrow that mimics falling sand. The zip file also contains a number<br>
of "sand guns" with various periods (thanks to Dean Hickerson).<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/Snakes.zip'>Snakes</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Snakes is a rule by Dean Hickerson in which thin snake-like objects appear to move randomly.<br>
For more details, see README.txt in the zip file.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/files/ships2.zip'>Ships</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A rule by Alan Tennant, for construction of large 4 state ships. Based on discoveries in WWEJ3.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/svn/trunk/downloads/Pilot.zip'>Pilot</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
Pilot - rule with a 2-cell spaceship - it was meant to multiply by collisions and it showed up, that bigger soups are exploding.<br>
</td></tr></table></td></tr>
<tr><td width='20%'><b>
<a href='get:http://ruletablerepository.googlecode.com/svn/trunk/downloads/BHL_traffic.zip'>Biham-Middleton-Levine traffic model</a>
</b></td><td><table cellpadding='4' border='0' cellspacing='0' width='100%'><tr><td>
A self-organizing cellular automaton traffic flow model. It consists of a number of cars represented by points on a lattice with a random starting position, where each car may be one of two types: those that only move downwards (blue), and those that only move towards the right (red).<br>
</td></tr></table></td></tr>
</table>
</p></blockquote>



&lt;/body&gt;




&lt;/html&gt;
