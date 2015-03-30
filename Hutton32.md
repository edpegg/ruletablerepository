# Introduction #

Tim Hutton modified the [Nobili32](Nobili32.md) ruleset to allow simpler construction and rotational invariance. This has led to him being able to construct a form of replicator based on a repeater-emitter loop, similar to Langton's loops.



# Details #

In Nobili's cellular automaton, automatic retraction is achieved by modifying the constructor to send a 'retract' pulse after constructing each cell. Moreover, two parallel wires, one composed of ordinary transmission states and the other composed of special transmission states, are required to allow articulation. This results in bulky organs, as in von Neumann's original rule.

In Hutton's rule, on the other hand, auto-retraction is automatically controlled by the rules themselves. This is accomplished by allowing ordinary transmission states to become special transmission states when in close proximity to a sensitised (transition) state. There is also a signal train allowing a simple retraction (101111).

The existence of a retraction operation means that a single wire is sufficient for a universal construction arm. This is demonstrated in both Hutton's replicator and the 'golly-constructor.rle' file. The advantage of having one wire is that signal trains are generally shorter, and that there is no need to worry about synchronisation. In Nobili's and von Neumann's rules, bending the construction arm results in one path extending more than the other path (this is the principle behind bimetallic strips).

Instead of using anisotropic signal trains such as 'construct east-directed OTS', rotationally invariant commands such as 'construct forward OTS' are used. This property, combined with the other features, allows the construction arm to move as freely as the counterpart in Codd's cellular automaton.

Rotational invariance also means that the machine can construct itself in different orientations. This results in the pattern being able to produce two copies per cycle, each at a different orientation, theoretically allowing exponential growth. However, the replicators soon collide into each other, reducing this to quadratic growth.

Hutton's replicator contains a simple repeater-emitter loop, like Langton's loops. This means that the instructions are interpreted very quickly, unlike in the classic replicators of von Neumann's and Nobili's cellular automata. More specifically, Hutton's replicator reads the instruction in linear time, whereas the others read them in quadratic time. Hutton's replicator takes just 44,201 timesteps to replicate.

Note that an active tape is not a prerequisite for linear tape-reading. It is possible to build a machine that uses clocks to constantly send out pulses, which are used to read the tape. Adam P. Goucher has built [a configuration](http://ruletablerepository.googlecode.com/files/linear-constructor.zip) in Nobili's rule that replicates in just 2.08 million generations, which is over three orders of magnitude faster than any other replicator in the rule. Hutton's ingenious replicator is still over 40 times faster!

The body of Tim hutton's replicator, excluding the tape, is very small compared to the replicators of von Neumann's and Nobili's cellular automata. Indeed, it is compact due to its simplicity - it is nowhere near as complex as the classic replicators. The corpus of the machine only performs the following operations:

  1. detect a unique mark on the tape as it goes round.
  1. starts and stops a 6-period clock, which extends the tape.
  1. codes for: extend, turn left, turn left, extend some more.
  1. counts when 3 tape marks have gone past, and switches coder.
  1. when finished writing an empty tape of the right length, divert the tape to copy itself into the new holder.
  1. after the tape is copied across, it separates itself from its old tape to prevent infection spreading from multiple copies.

The corpus of the replicator is shown below:


![http://www.sq3.org.uk/files/modJVN_body.png](http://www.sq3.org.uk/files/modJVN_body.png)


As you can see, Nobili's quiescent crossover has been used extensively throughout the machine. Even though Hutton accepted this modification of Nobili's, he discarded the other modification; in Hutton's cellular automaton, excited confluent states are now no longer able to store information.


Modifying the rules meant that he had to remove some of the functionality of the original rules. Ordinary transmission states can no longer annihilate special transmission states. In von Neumann's and Nobili's cellular automata, this feature was used in the construction arm and tape reader. Hutton's rule still supports the converse: special transmission states can destroy ordinary transmission states. Tim Hutton conjectures that his modifications do not compromise the computation- and construction-universality of the cellular automaton.