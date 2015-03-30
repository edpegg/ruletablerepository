# Introduction #

John von Neumann originally devised a kinematic model of self-replication. However, since this was based on physical principles, it was extremely difficult to mathematically formalise. Instead, he decided to opt for a mathematical abstraction. He attempted to create a model based on partial differential equations, the versatile mathematics that models the fundamental forces of our Universe.

Stanislaw Ulam suggested that he use a lattice, rather than continuous space. John von Neumann decided to use the following rules:

  * The universe is defined on an infinite square grid.
  * Time is updated in discrete iterations, or timesteps.
  * Each square (known thereafter as a 'cell') can be in any of 29 states in any timestep.
  * The next state of each cell is dependent on its current state and the states of the surrounding four neighbours.

The cellular automaton was born!


# Details #


## The states ##

The 29 states are divided into 5 subsets:


One ground state:


  * 0) The ground state, U


Eight sensitised states:


  * 1) S
  * 2) S<sub>0</sub>
  * 3) S<sub>1</sub>
  * 4) S<sub>00</sub>
  * 5) S<sub>01</sub>
  * 6) S<sub>10</sub>
  * 7) S<sub>11</sub>
  * 8) S<sub>000</sub>


Eight ordinary transmission states:


  * 9) East-directed quiescent ordinary transmission state
  * 10) North-directed quiescent ordinary transmission state
  * 11) West-directed quiescent ordinary transmission state
  * 12) South-directed quiescent ordinary transmission state
  * 13) East-directed excited ordinary transmission state
  * 14) North-directed excited ordinary transmission state
  * 15) West-directed excited ordinary transmission state
  * 16) South-directed excited ordinary transmission state


Eight special transmission states:


  * 17) East-directed quiescent special transmission state
  * 18) North-directed quiescent special transmission state
  * 19) West-directed quiescent special transmission state
  * 20) South-directed quiescent special transmission state
  * 21) East-directed excited special transmission state
  * 22) North-directed excited special transmission state
  * 23) West-directed excited special transmission state
  * 24) South-directed excited special transmission state


Four confluent states:


  * 25) C<sub>00</sub> (quiescent for both cycles)
  * 26) C<sub>01</sub> (quiescent, but will be excited next cycle)
  * 27) C<sub>10</sub> (excited, but will be quiescent next cycle)
  * 28) C<sub>11</sub> (excited for both cycles)


## The rules ##

Transmission states carry information at a rate of one bit per timestep. An excited transmission state represents a '1' and a quiescent transmission state represents a '0'. Excited OTSs annihilate STSs and vice-versa. A confluent state can be used to transfer information from an OTS to a STS. An excited STS, however, will destroy the confluent cell.

If a signal reaches the end of a wire, it will create a sensitised state. The following arrangement of signal pulses will determine the cell that the sensitised state will transform into. This is used for constructing arbitrary quiescent configurations.

A confluent state contains two bits of information, and acts as a delay. A confluent state can act as a fanout device, allowing pulses to be duplicated. Finally, if the confluent state has two or more inputs, it acts as an AND gate. The output of the confluent state is the logical conjunction of its inputs.

![http://upload.wikimedia.org/wikipedia/commons/5/50/VonNeumann_CA_demo.gif](http://upload.wikimedia.org/wikipedia/commons/5/50/VonNeumann_CA_demo.gif)


## Configurations ##

The animation shows a very simple configuration, which consists of a loop of ordinary transmission states connected to a line of special transmission states via a confluent state. A packet of information continually loops around the configuration; the confluent state duplicates this information and transfers it to the line of special transmission states. When the signals reach the end of the line, they trigger the production of a sensitised state. The following signals cause it to become an east-directed STS. Hence, the line will continue increasing in length.

Replicators are far more complex. They usually comprise a corpus of approx. 20 000 cells, and a long tape extending to the right. The corpus itself is composed of tape-reading and construction devices, together with a number of organs that decode and encode signal trains. They also require some form of memory to remember the previous bits of an instruction. This usually requires the use of special transmission states. William R. Buckley has devised three self-constructing configurations in this rule, one of which is a [partial constructor](PartialConstructor.md).

Complex devices generally require signals to be crossed. This is not a trivial problem: for individual pulses it can be solved by a small, quiescent configuration, whereas crossing entire packets is accomplished by a much larger, active configuration. Renato Nobili modified the rules to eliminate this problem, but William R. Buckley demonstrated that these modifications are superfluous; for any configuration in [Nobili's rule](Nobili32.md), an equivalent, but larger, counterpart can be constructed in von Neumann's original rule.