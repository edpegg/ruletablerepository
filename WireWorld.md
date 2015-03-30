# Introduction #

Wireworld is a cellular automaton that can simulate logic circuits. It draws inspiration from actual electronic circuits, where electrons (or rather, the charges carried by them) travel through copper wires. Wireworld is a lot simpler than actual electronic circuits, as Kirchoff's laws, resistance etc. do not apply.


# Details #

The rule operates on the Moore neighbourhood, and has four states:

  * Empty space (insulator)
  * Electron head
  * Electron tail
  * Wire (conductor)

Since the wires are not themselves directed, the pulses need two parts (head and tail) in order to know which way the pulse is travelling. The rules are very simple:

  * Empty space always remains as empty space.
  * Electron head always degenerates into electron tail.
  * Electron tail always changes to wire.
  * Wire remains as wire, unless it is surrounded by exactly 1 or 2 electron heads, in which case it becomes an electron head.

These simple rules are sufficient to simulate any logic gate or finite computer, up to and including a programmable computer. Since the copper wire cannot expand, no finite pattern can expand to hold an arbitrary amount of memory.

For examples of such circuits, see the sites below:

http://www.quinapalus.com/wi-index.html

http://pages.prodigy.net/nylesheise/wireworld.html

http://en.wikipedia.org/wiki/Wireworld

http://www.with-logic.co.uk/WireWorld.htm

Here is a picture of a programmable computer. The program and data are stored in the machine's 64 16-bit registers. The program included calculates prime numbers up to 65535 and displays them in the seven-segment display:

![http://www.zen6741.zen.co.uk/quinapalus/ww800x600.gif](http://www.zen6741.zen.co.uk/quinapalus/ww800x600.gif)