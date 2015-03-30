# Introduction #

Renato Nobili extended von Neumann's 29-state CA to allow easier crossing of wires, leading to enormously simpler machines. Nobili modified the rules so that the confluent state can act as an ideal signal crossing. He also allowed excited confluent states to store data.


**Rule Table:** [Nobili32.table](http://www.sq3.org.uk/files/Nobili32.table)

http://ruletablerepository.googlecode.com/files/nobili32-big.PNG

# Details #

## Signal crossing ##

In the 29-state CA, pulse signal crossing requires a 4x5 configuration. This is demonstrated in William R. Buckley's 'Sphinx' replicator. To achieve packet signal crossing, more complex devices are required. The smallest possible is a 8x8 configuration devised by Gorman, known as the real-time crossing organ, or RTCO. An alternative, which is easier to construct, is the MCO, which comprises three XOR gates. Both of these crossing organs require synchronisation.

However, Nobili added an extra three states (confluent state with vertical signal, confluent state with horizontal signal and confluent state with both horizontal and vertical signals) to allow ideal signal crossing using a passive configuration. Buckley demonstrated the surplusness of Nobili's modification by constructing two pairs of configurations. These four self-replicators are shown in this [PDF file](http://uncomp.uwe.ac.uk/automata2008/buckley/buckley.pdf).


## Example replicators ##

Golly includes four self-replicating configurations in this rule. NP-replicator, made by Nobili and Pesavento, was the first self-replicating configuration of von Neumann's design.

N-compressed replicator uses run-length encoding to reduce the size of the tape. Each instruction is coded in two parts: The first part is the codon itself; the second part is the number of times to repeat it. This is handled by a specialised organ. However, this results in a larger corpus than a basic replicator.

Buckley's two designs, codon5-auto-retract and codon4-auto-retract, compromise between tape compression and corpus size to minimise the tape length. The first one uses five-bit codons, and is more efficient than the previous replicators due to its 'auto-retract' feature. When a cell is written, the construction arm automatically retracts one cell. The second one is optimised even further: An extra bit is generated internally, resulting in instructions being only four bits, rather than five bits, long.


# Patterns #

| **pattern name** | **description** | **author** |
|:-----------------|:----------------|:-----------|
| [codon5-auto-retract.rle](http://golly.cvs.sourceforge.net/viewvc/*checkout*/golly/golly/src/Patterns/JvN/codon5-auto-retract.rle) | The first replicator with auto-retraction capabilities. | William R. Buckley |
| [codon4-auto-retract.rle](http://golly.cvs.sourceforge.net/viewvc/*checkout*/golly/golly/src/Patterns/JvN/codon4-auto-retract.rle) | A modification of the above replicator, which uses a four-bit instead of five-bit code. | William R. Buckley |
| [N-compressed-replicator.rle](http://golly.cvs.sourceforge.net/viewvc/*checkout*/golly/golly/src/Patterns/JvN/N-compressed-replicator.rle) | A replicator that uses run-length encoding to reduce the size of the tape. | Renato Nobili |
| [NP-replicator.rle.gz](http://golly.cvs.sourceforge.net/viewvc/*checkout*/golly/golly/src/Patterns/JvN/NP-replicator.rle.gz) | The very first replicator that conforms to von Neumann's design specifications. Due to an oversight when designing the machine, the tape had to be 'bodged' so that it could replicate successfully. This involved merging the corpus and tape of the replicator. | Renato Nobili, Umberto Pesavento |
| [linear-constructor.zip](http://ruletablerepository.googlecode.com/files/linear-constructor.zip) | The fastest replicator in the rule, which takes 2.08 million generations to replicate. | Adam P. Goucher |