<h1>Contents:</h1>




# Introduction #

Golly 2.5 introduces a new format for specifying rules.
A file in the new format has a .rule extension and contains all the information about the rule:
its name, documentation, table/tree data (used by the RuleLoader algorithm), and any color/icon information.

Before describing the syntax in detail, let's look at an example.
Here is WireWorld.rule (supplied in Golly's Rules folder):

```
@RULE WireWorld

A 4-state CA created by Brian Silverman.  WireWorld models the flow of
currents in wires and makes it relatively easy to build logic gates
and other digital circuits.

@TABLE

# Golly rule-table format.
# Each rule: C,N,NE,E,SE,S,SW,W,NW,C'
#
# Default for transitions not listed: no change
#
# Variables are bound within each transition. 
# For example, if a={1,2} then 4,a,0->a represents
# two transitions: 4,1,0->1 and 4,2,0->2
# (This is why we need to repeat the variables below.
#  In this case the method isn't really helping.)
#
n_states:4
neighborhood:Moore
symmetries:rotate8
var a={0,1,2,3}
var b={0,1,2,3}
var c={0,1,2,3}
var d={0,1,2,3}
var e={0,1,2,3}
var f={0,1,2,3}
var g={0,1,2,3}
var h={0,1,2,3}
var i={0,2,3}
var j={0,2,3}
var k={0,2,3}
var l={0,2,3}
var m={0,2,3}
var n={0,2,3}
1,a,b,c,d,e,f,g,h,2
2,a,b,c,d,e,f,g,h,3
3,i,j,k,l,m,n,a,1,1
3,i,j,k,l,m,1,n,1,1
3,i,j,k,l,1,m,n,1,1
3,i,j,k,1,l,m,n,1,1

@NAMES

# these state names are not yet used by Golly
0 empty
1 electron tail
2 electron head
3 copper wire

@COLORS

# same colors used at http://www.quinapalus.com/wi-index.html

0  48  48  48   dark gray
1   0 128 255   light blue
2 255 255 255   white
3 255 128   0   orange

@ICONS

# icon info is in XPM format (order is not important)

XPM
/* width height num_colors chars_per_pixel */
"31 31 5 1"
/* colors */
". c #000000"
"D c #404040"
"C c #808080"
"B c #C0C0C0"
"W c #FFFFFF"
/* pixels */
"..............................."
"..............................."
"..........DCBWWWWWBCD.........."
".........CWWWWWWWWWWWC........."
".......DWWWWWWWWWWWWWWWD......."
"......BWWWWWWWWWWWWWWWWWB......"
".....BWWWWWWWWWWWWWWWWWWWB....."
"....DWWWWWWWWWWWWWWWWWWWWWD...."
"....WWWWWWWWWWWWWWWWWWWWWWW...."
"...CWWWWWWWWWWWWWWWWWWWWWWWC..."
"..DWWWWWWWWWWWWWWWWWWWWWWWWWD.."
"..CWWWWWWWWWWWWWWWWWWWWWWWWWC.."
"..BWWWWWWWWWWWWWWWWWWWWWWWWWB.."
"..WWWWWWWWWWWWWWWWWWWWWWWWWWW.."
"..WWWWWWWWWWWWWWWWWWWWWWWWWWW.."
"..WWWWWWWWWWWWWWWWWWWWWWWWWWW.."
"..WWWWWWWWWWWWWWWWWWWWWWWWWWW.."
"..WWWWWWWWWWWWWWWWWWWWWWWWWWW.."
"..BWWWWWWWWWWWWWWWWWWWWWWWWWB.."
"..CWWWWWWWWWWWWWWWWWWWWWWWWWC.."
"..DWWWWWWWWWWWWWWWWWWWWWWWWWD.."
"...CWWWWWWWWWWWWWWWWWWWWWWWC..."
"....WWWWWWWWWWWWWWWWWWWWWWW...."
"....DWWWWWWWWWWWWWWWWWWWWWD...."
".....BWWWWWWWWWWWWWWWWWWWB....."
"......BWWWWWWWWWWWWWWWWWB......"
".......DWWWWWWWWWWWWWWWD......."
".........CWWWWWWWWWWWC........."
"..........DCBWWWWWBCD.........."
"..............................."
"..............................."

XPM
/* width height num_colors chars_per_pixel */
"15 15 4 1"
/* colors */
". c #000000"
"D c #404040"
"B c #C0C0C0"
"W c #FFFFFF"
/* pixels */
"..............."
"....DBWWWBD...."
"...BWWWWWWWB..."
"..BWWWWWWWWWB.."
".DWWWWWWWWWWWD."
".BWWWWWWWWWWWB."
".WWWWWWWWWWWWW."
".WWWWWWWWWWWWW."
".WWWWWWWWWWWWW."
".BWWWWWWWWWWWB."
".DWWWWWWWWWWWD."
"..BWWWWWWWWWB.."
"...BWWWWWWWB..."
"....DBWWWBD...."
"..............."

XPM
/* width height num_colors chars_per_pixel */
"7 7 4 1"
/* colors */
". c #000000"
"D c #404040"
"E c #E0E0E0"
"W c #FFFFFF"
/* pixels */
".DEWED."
"DWWWWWD"
"EWWWWWE"
"WWWWWWW"
"EWWWWWE"
"DWWWWWD"
".DEWED."
```


# The syntax of a .rule file #

The .rule format is textual and consists of one or more sections.
Each section starts with a line of the form @XXX... where X is an uppercase letter.
If there is more than one section with the same name then only the first one is used.
Any unrecognized sections are silently ignored -- this will allow us to add new
sections in the future without breaking old versions of Golly.
The currently recognized sections are described below.


## @RULE ##

This is the only mandatory section. The first line of a .rule must start with @RULE followed by a space
and then the rule name. For example:
```
@RULE WireWorld
```
The supplied rule name must match exactly the name of the .rule file. This helps Golly to avoid problems
that can occur on case-sensitive file systems. When naming a new rule it's best to stick to the following
conventions, especially if you'd like to share the .rule file with other Golly users:

  * Please capitalize all rule names and create files like Foo.rule rather than foo.rule. This helps to emphasize that rule names are important, especially on case-sensitive file systems. If the rule "foo" is specified inside a .rle or .mc file then Golly won't be able to find Foo.rule on a case-sensitive system like Linux.

  * To allow for possible future extensions in the way Golly handles rule names, it's best to use only letters and digits. Hyphens and underscores are also okay if you need some sort of separator. Hyphens can allow a set of related rules to share colors and/or icons (see [below](#Related_rules_can_share_colors_and/or_icons.md)). Note in particular that spaces and colons must not be used.

After the @RULE line and before the next section (or end of file) you can include any amount of arbitrary text,
so this is the place to include a description of the rule or any other documentation.
If the .rule file has a @TREE section that was created by a Python transition function
then this is a good place to put the Python code.


## @TABLE ##

This section is optional. If present, it contains a transition table that can be loaded by the RuleLoader algorithm.
The contents of this section is identical to the contents of a .table file.
A detailed specification is available in TheFormat page.


## @TREE ##

This section is optional. If present, it contains a rule tree that can be loaded by the RuleLoader algorithm.
(If a .rule file also contains a @TABLE section, RuleLoader will use the first one it finds.)
The contents of this section is identical to the contents of a .tree file.

A detailed description of a rule tree can be found in Golly's Help > File Formats, but most people don't
need to know these details because Golly provides a number of tools for creating rule trees.
The make-ruletree.py script in Scripts/Python/Rule-Generators can convert a Python transition function
(passed via the clipboard) into a rule tree.  The script will either create a new .rule file or update the @TREE
section in an existing .rule file.  Another script, RuleTableToTree.py, does much the same job using a
requested .table file as input.

There are also programs in Rules/TreeGenerators that can transform a given transition function in
C++, Perl, or Java into a .tree file.  The contents of the .tree file can then be copied into the @TREE section
of a .rule file.


## @COLORS ##

This section is optional and can be used to specify the RGB colors for one or more states using lines
with 4 numbers, like these:
```
0  48  48  48   dark gray
1   0 128 255   light blue
2 255 255 255   white
3 255 128   0   orange
```
Golly silently ignores any states that are invalid for the rule.
To specify a color gradient for all live states (all states except 0) you can use a line with 6 numbers,
like this:
```
255 0 0  0 0 255   red to blue
```
In both cases, any text after the final number on each line is ignored.
Blank lines or lines starting with "#" are also ignored.

Note that a .rule file is loaded after switching to the current algorithm's default color scheme,
so you have the choice of completely changing all the default colors, or only changing some of them.
Use Preferences > Color if you want to change the default colors.


## @ICONS ##

This section is optional and can be used to override the default icons displayed for this rule
(when Golly is in icon mode).


### Specifying icons using XPM ###

Icon bitmaps can be specified using a simple subset of the XPM format.
Here's a small example that describes two 7x7 icons suitable for a 3-state rule
(icons are never used for state 0):
```
XPM
/* width height num_colors chars_per_pixel */
"7 14 2 1"
/* colors */
". c #000000"
"A c #FFFFFF"
/* icon for state 1 */
"A......"
".A....."
"..A...."
"...A..."
"....A.."
".....A."
"......A"
/* icon for state 2 */
"......A"
".....A."
"....A.."
"...A..."
"..A...."
".A....."
"A......"
```
Any blank lines or lines starting with "#" or "/" are ignored. A line with XPM by itself indicates the start of a set of icon bitmaps at a particular size. The @ICONS section can contain any number of XPM subsections, and their order is not important. Three different icon sizes are currently supported: 7x7, 15x15 and 31x31 (for displaying at scales 1:8, 1:16 and 1:32 respectively). Any missing icon sizes will be created automatically by scaling a supplied size. Scaled icons can look rather ugly, so if you want good looking icons it's best to supply all three sizes.

After seeing an XPM line, Golly then looks for lines containing strings delimited by double quotes. The first double quote must be at the start of the line (any text after the second double quote is ignored). The first string contains crucial header information in the form of 4 positive integers:

  * The 1st number is the bitmap's width which also defines the icon size. If it is not 7, 15 or 31 then Golly simply ignores the rest of the XPM data. (This provides upward compatibility if we ever decide to support more sizes.)

  * The 2nd number is the bitmap's height. This must be an integer multiple of the width — the number of icons is the height divided by the width.

  * The 3rd number is the total number of different colors used in the bitmap. After the first string comes the strings that specify each color.

  * The 4th number is the number of characters used to specify each pixel and must be 1 or 2. After the color strings comes the strings with the pixel data for each row of the bitmap. Each such string should contain width × chars\_per\_pixel characters.

The total number of strings after the XPM line should be 1 + num\_colors + height. You'll get an error message if there aren't enough strings. Any extra strings are ignored.

The 1st icon specified is for state 1, the 2nd is for state 2, etc. If the number of icons supplied is fewer than the number of live states then the last icon is automatically duplicated. If there are more icons than required then the extra icons are simply ignored.


### Grayscale icons or multi-color icons ###

Golly recognizes two types of icons: grayscale or multi-color. Grayscale icons only use shades of gray (including black and white), as in the above example. Any black areas will be transparent; ie. those pixels will be replaced by the color for state 0. White pixels will be replaced by the color for the cell's current state. Gray pixels are used to do anti-aliasing; ie. the darker the gray the greater the transparency. Using grayscale icons minimizes the amount of XPM data needed to describe a set of icons, especially if the icons use the same shape for each state (as in WireWorld.rule).

If a set of icons contains at least one color that isn't a shade of gray then the icons are said to be multi-colored. Any black pixels are still converted to the state 0 color, but non-black pixels are displayed without doing any substitutions.
If you want to use multi-colored icons then you'll probably want a @COLORS section as well so that the non-icon colors match the icon colors as closely as possible. For example, if the icon for state 1 consists of red and blue triangles then it would be best to set the color of state 1 to purple in the @COLORS section. This minimizes "color shock" when switching between icon and non-icon display mode.


### Requesting built-in icons ###

Instead of specifying icon bitmaps using XPM data, you might prefer to use Golly's built-in
grayscale icons by supplying one of the following words on a line by itself:

  * **circles** — circular icons (normally used for Moore neighborhood rules).

  * **diamonds** — diamond-shaped icons (normally used for von Neumann neighborhood rules).

  * **hexagons** — hexagonal icons (normally used for hexagonal neighborhood rules).

  * **triangles** — triangular icons (only suitable for a 4-state rule that is emulating a triangular neighborhood).


### Tools for creating icons ###

One way to create XPM icons is to use a painting application that can write .xpm files.
Their contents can then be pasted into a .rule file with a small amount of editing.

Another way is to use two new scripts supplied with Golly 2.5 called icon-importer.py
and icon-exporter.py (both can be found in Scripts/Python/Rule-Generators).
These scripts allow Golly to be used as an icon editor.  Here's how:

**Step 1:** Switch to the rule whose icons you wish to change or create
and then run icon-importer.py.
This will create a new layer called "imported icons for _rulename_"
(the name will be used by icon-exporter.py, so don't change it).
The script searches for _rulename_.rule in your rules folder, then in
the supplied Rules folder.  If found, it extracts any @ICONS data
and displays the icon bitmaps in gray boxes.  The location of these
boxes will be used by icon-exporter.py, so don't move them.

If the @ICONS data is missing icons at a particular size then the script creates
them by scaling up or down an existing set of icons.  For example, missing
31x31 icons will be created by scaling up the 15x15 icons.

The new layer uses a Generations rule with the maximum number of
states (//256) so we can have lots of colors.  The initial palette contains
a grayscale gradient from white to black, followed by the colors used in the
imported icons (if any), followed by three rainbow gradients (bright, pale, dark).
You can change these colors by using Layer > Set Layer Colors.

**Step 2:** Edit the icon bitmaps using Golly's editing capabilities.
Golly isn't as powerful as a full-blown painting app, but hopefully it's
sufficient for such small images.

**Step 3:** When you've finshed editing, run icon-exporter.py.
This script will extract the icon data and create a suitable @ICONS section
in _rulename_.rule in your rules folder (the script will never create or
modify a .rule file in the supplied Rules folder).
If _rulename_.rule already exists in your rules folder
then the script _replaces_ any existing @ICONS section (and any
@COLORS section if the icons are multi-color) so it won't clobber
any other info in the file.

If _rulename_.rule doesn't exist in your rules folder then it will be
created.  This file won't have any @TABLE or @TREE section, but
that's perfectly valid.  It means either the rule is built-in
(ie. recognized by a non-RuleLoader algorithm),
or else _rulename_.rule also exists in the supplied Rules folder and
so the RuleLoader algorithm will use that file when it can't find any
@TABLE or @TREE section in the .rule file in your rules folder.

Finally, icon-exporter.py creates a new layer called "icon test" which
uses the original rule and displays a simple pattern containing
all live states so you can check what the new icons look like.


# How Golly finds .rule files #

There are two situations where Golly needs to look for a .rule file:

1. If the RuleLoader algorithm is asked to switch to a rule called "Foo" then it first
looks for Foo.rule in your user-specific rules folder
(the location of this folder can be changed in Preferences > Control).
If not found, or if Foo.rule has no @TABLE or @TREE section, it will then look
for Foo.rule in the supplied Rules folder.  If Foo.rule doesn't exist then it will
use the same search procedure to look for Foo.table, then Foo.tree.

2. After switching to a new rule (not necessarily using RuleLoader), Golly needs
to look for color and/or icon information specific to that rule.  A similar search procedure
to the one above is used again, where this time Golly looks for any @COLORS and/or @ICONS
sections in Foo.rule.  (Unlike the above search, if Foo.rule is found in your rules folder but
doesn't have any color/icon info then Golly will _not_ look for Foo.rule in the Rules folder.)

Note that the 2nd search always occurs after clicking OK in the Control menu's Set Rule dialog,
even if the current rule wasn't changed.  This is a quick way to test changes to a .rule file.


# Related rules can share colors and/or icons #

If _rulename_.rule is missing either the @COLORS or @ICONS section, Golly checks to see if _rulename_
contains a hyphen.  If it does then it looks for the missing color/icon data in another .rule file
called _prefix_-shared.rule where _prefix_ consists of all the characters before the _final_ hyphen.
(As in the above searches, it looks in your rules folder first, then in the supplied Rules folder.)
This allows related rules to share a single source of colors and/or icons.

For example, suppose you have a set of related rules in files called Foo-1.rule, Foo-2.rule, etc.
If you want all these rules to use the same colors then create a file called Foo-shared.rule:

```
@RULE Foo-shared
This file contains the colors shared by Foo-* rules.

@TABLE
n_states:3
neighborhood:Moore
symmetries:none
# do nothing

@COLORS
0 0 0 0     black
1 255 0 0   red
2 0 0 255   blue
```

Note that a shared .rule file should contain a valid @TABLE section with an
appropriate value for n\_states (the neighborhood setting doesn't really matter,
as long as it's legal).  This allows the RuleLoader algorithm to load it, which
means you can switch to the Foo-shared rule in case you want to add/edit
icons using icon-importer.py.

For another good example, see Worm-shared.rule in Golly's Rules folder.
It contains the icons shared by all the other Worm-`*` rules.


# How to override a supplied or built-in rule #

The search procedure described above makes it easy to override a supplied .rule file,
either completely or partially.  Note that there is never any need to add or modify files
in the supplied Rules folder.  For example, if you want to override the colors and icons
used in the supplied WireWorld.rule then you can create a file with the same name in
your rules folder.  Its contents might look like this:

```
@RULE WireWorld

@COLORS
0 0 0 0               black background
0 255 0   255 255 0   live states fade from green to yellow

@ICONS
diamonds
```

It's also possible to override a built-in rule (ie. a rule recognized by an algorithm other than
RuleLoader).  A built-in rule name can contain characters not allowed in file names ("/" and "\"),
so Golly will substitute those characters with underscores when looking for the corresponding
.rule file. For example, if you want to change the colors and/or icons for Life (B3/S23)
then you'll need to create a file called B3\_S23.rule.  This example uses a multi-colored icon
to show a blue sphere on a white background:

```
@RULE B3_S23

Override the default colors and icons for Life (B3/S23).

@COLORS

0 255 255 255   white (matches icon background below)
1 54 54 194     dark blue (average color of icon below)

@ICONS

# 7x7 and 15x15 icons will be created by scaling down this 31x31 icon:

XPM
/* width height num_colors chars_per_pixel */
"31 31 78 2"
/* colors */
".. c #FFFFFF"   white background
"BA c #CECEDE"
"CA c #7B7BAD"
"DA c #4A4A84"
"EA c #18187B"
"FA c #08006B"
"GA c #18186B"
"HA c #29297B"
"IA c #6B6BAD"
"JA c #ADADDE"
"KA c #EFF7FF"
"LA c #ADADC6"
"MA c #39398C"
"NA c #3939BD"
"OA c #7B7BCE"
"PA c #ADB5DE"
"AB c #8C8CD6"
"BB c #4A4A9C"
"CB c #18188C"
"DB c #EFEFEF"
"EB c #EFEFFF"
"FB c #525A9C"
"GB c #08088C"
"HB c #ADADE7"
"IB c #DEDEEF"
"JB c #D6D6F7"
"KB c #DEE7F7"
"LB c #BDBDEF"
"MB c #525ABD"
"NB c #21219C"
"OB c #292984"
"PB c #CECEE7"
"AC c #ADB5CE"
"BC c #2929BD"
"CC c #7B7BDE"
"DC c #BDC6E7"
"EC c #CECEF7"
"FC c #8C8CE7"
"GC c #4242C6"
"HC c #A5A5BD"
"IC c #08087B"
"JC c #3939CE"
"KC c #5A5AC6"
"LC c #BDBDF7"
"MC c #BDBDDE"
"NC c #6B6BD6"
"OC c #9494DE"
"PC c #3931DE"
"AD c #1818AD"
"BD c #2929CE"
"CD c #9C9CC6"
"DD c #10087B"
"ED c #9C9CBD"
"FD c #1818B5"
"GD c #1818C6"
"HD c #847BCE"
"ID c #181094"
"JD c #6B6BCE"
"KD c #7B7BB5"
"LD c #2121AD"
"MD c #BDC6D6"
"ND c #0808AD"
"OD c #4A42B5"
"PD c #00009C"
"AE c #3942BD"
"BE c #3129B5"
"CE c #B5B5CE"
"DE c #0000BD"
"EE c #0000CE"
"FE c #0000DE"
"GE c #42427B"
"HE c #C6CECE"
"IE c #0000EF"
"JE c #9494AD"
"KE c #F7FFEF"
"LE c #10086B"
"ME c #7B849C"
"NE c #0000F7"
/* icon for state 1 */
".............................................................."
".............................................................."
"......................BACADAEAFAGAHAIAJA......................"
"................KALAMAFANAOAJAPAJAABBBCBEAIADB................"
"..............EBFBGBNAHBIBDBJBKAKBEBJBLBMBNBOBPB.............."
"............ACHABCCCDCECIBPBJBPBIBPBJBIBECFCGCCBCAKA.........."
"..........HCICJCKCLBLCLBMCLBLBLBLBMCLBLBMCLCNCJCCBCAKA........"
"........DBOBBCJCCCJAJAJAJAJAJAJAJAJAJAJAJAJAOCJCPCICAC........"
"......KADAADBDBCABABOCABOCOCOCOCABOCABOCABCDFCJCBDBCDDBA......"
"......EDGBFDGDADCCABOAOAOAOAOAOAOAOAHDOAHDCCCCNAADGDIDMA......"
"....KAHAADFDFDADJDMBOAJDJDJDJDJDKDJDJDJDJDJDJDLDFDFDFDICBA...."
"....MDFANDNDNDADODMBMBMBMBMBMBMBKCKCMBMBMBMBODADNDNDNDGBIA...."
"....CAGBNDPDNDPDADGCODODODODODODNAODODGCODAEBCPDNDPDNDPDGA...."
"....OBPDPDNDPDNDNDADBCBEBCBEBCBCBEBCBCBCNAADPDNDNDPDPDNDICPB.."
"....ICNDNDPDNDNDNDPDNDADADADADADADADADADNDNDNDNDNDNDNDPDGBCE.."
"....FANDNDDENDNDNDDENDDENDNDNDNDNDNDNDNDNDNDNDNDNDNDNDNDGBLA.."
"....FANDDENDDEDENDDEDENDDENDDEDEDEDEDEDEDEDEDEDEDENDDEDEGBED.."
"....GANDEEDEDEDEDEDEDEDEDEDEDEDENDDENDDEDEDEDEDEDEDEDEDEGBLA.."
"....BBPDEEDEEEDEEEDEEEDEEEDEDEDEEEDEEEDEDEDEDEDEEEDEEEDEFABA.."
"....EDGBDEEEDEEEEEEEDEEEDEEEEEEEEEEEEEEEEEEEEEEEEEDEEENDGADB.."
"....KBICDEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEEGBDA...."
"......FBNDFEFEEEEEEEEEFEEEEEFEEEEEEEEEEEEEEEEEEEEEFEDEICHC...."
"......IBEADEFEFEEEFEFEFEFEFEEEFEFEFEFEFEFEFEFEFEFEDEGBGEDB...."
"........LAGBFEFEFEFEFEFEFEFEFEFEFEFEFEFEFEFEFEFEFENDGAHE......"
"..........FBNDFEFEIEFEFEIEIEIEFEIEFEFEIEFEFEFEFEEEDDJEKE......"
"..........EBFBIDEEIEIEIEFEFEFEIEFEIEIEIEIEIEIENDLEMEKE........"
"..............CDGBDEIEIENENEIEIEIEIEIEIEIEGDPDGAJEKE.........."
"................BAOBGBADFEIENEIENEIEIEEENDFAGECEKE............"
"....................CDBBDDPDIDNDADPDICEAGEJEDB................"
"........................EBBALAEDEDHCMCDBKE...................."
".............................................................."
```


# The easy way to install a new .rule file #

Golly provides a quick and easy way to create a new .rule file in the right place.
Simply copy the rule contents to the clipboard, then select the Open Clipboard
command (in the File menu) or the Paste command (in the Edit menu).
If the first line of the clipboard starts with "@RULE rulename" then Golly will
save the text as rulename.rule in your rules folder (set in Preferences > Control)
and switch to that rule.


# Deprecated files (.table, .tree, .colors, .icons) #

Golly still supports the old rule-related files with extensions of .table, .tree, .colors and .icons,
but their use is discouraged.  To help speed up the transition to .rule files, Golly 2.5 has a
couple of handy features:

1. At the bottom of the Control menu is a new command called <b>Convert Old Rules</b>.
This will convert all .table/tree/colors/icons files into corresponding .rule files
(but existing .rule files will not be changed). It looks in the supplied Rules folder first,
then in your user-specific rules folder (set in Preferences > Control).
The results are displayed in the help window. If the conversion succeeds you'll be asked
if you want to delete the .table/tree/colors/icons files.

2. When Golly opens a .zip file containing .table/tree/colors/icons files it will automatically
convert them into .rule files, but only if the zip file has no .rule files.
Unlike the Convert Old Rules command, this conversion _will_ overwrite existing .rule files
(in case the zip file contents have changed).

Note that the downloadable zip files stored in the rule table repository have been modified
to include both .rule files and .table/tree/colors/icons files.  Golly 2.5+ will ignore the
deprecated files, while older versions of Golly will behave as before
(the .rule files will be treated as pattern files).