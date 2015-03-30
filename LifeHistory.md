# Introduction #

The LifeHistory rule is a seven-state superset of HistoricalLife,
allowing optional ON and OFF "marked" cells as well as history cells,
as well as a "start" ON state (#5), and a "killer" OFF state (#6)
intended to be used when impermeable boundaries are needed (e.g. to
separate subpatterns in a large stamp collection). This borrows ideas
and colors from Brice Due's `"BeforeAfterChange"` rule variants
from Mirek's Cellebration.

# Details #

Cell state 3 (marked ON = white) and state 5 ("start" ON = yellow) will
change to State 4 (marked OFF = red) when they die, and back to State 3
if they turn on again later. State 6 is gray.  Normal ON cells are green,
as in the optimized HistoricalLife rule.  State 3 is a slightly
greenish white to differentiate it from standard colors for
two-state Life, and State 2 is a darker shade of blue than in
HistoricalLife.

Pasting standard Life or HistoricalLife patterns into a LifeHistory
universe works cleanly, and the reverse is mostly true, too -- any
marked cells are lost.  Pasting HistoricalLife or LifeHistory patterns
into a regular two-state universe is fairly painful, because State 2
or 4 cells are automatically reduced to State 1 (instead of State 0).
In these cases, the conversion scripts should be used.

Python and Perl scripts included in the [LifeHistory archive file](http://ruletablerepository.googlecode.com/files/LifeHistoryRules.zip) make it easy to switch back and forth in Golly 2.0 between LifeHistory and standard two-state Life, even while a pattern is generating.  See the included readme.txt for more details.