# Set Associative Mapping

* Set associative mapping combines the best of direct and associative cache mapping.
* In this technique cache is divided into set of lines, by dividing cache the block can take place in any line of set this provides the flexibility of associative mapping.
* By creating sets in cache memory the number of conflict misses reduces because if a line of a particular set is accomodated by a block then new block can accomodate other line of same set.

### Hardware Orgnization

* When an address comes to cache memory, the cache contoller extracts the tag and set and offset bits.
* First the set bits are used to determine the particular set with the help of multiplexers.
* Then within set, the comparator compares the tag bits with each address line stored inside that particular set.
* If it thare is match then the the output of comparator is fed into the OR gate, to make output of OR gate HIGH indicating cache hit.
  * If the output of is LOW indicating cache Miss.
* After selecting the cache line the multiplexer is used to select the word within the line.

|Circuit Name|Size|No of circuits required|Reason|
|---|---|---|---|
|Comaprator|$N$-bit comparator, where $N$ = no of tag bits|No. of sets|the comparator compares the tag bits with a set, if we have $n$ sets then we require $n$ comparators.|
|OR|$2^n$ where $n$:set size, is the number of lines in a set|Number of Sets × (Associativity - 1)|the output of comparator is fed into the OR gate, that means we require a OR that has input equal to the number of lines per set.|
|Multiplexer|$2^{offsetBits}-to-1$|$S$ x $L$, S sets and L lines per set|It selcets the particular word within cache line, so if a line contains 64 word then we need $\log_2(64)-to-1$ mulitplexer.|

---

### Physcial bit spilit

  |Tag bits|Set bits|Block/line offset|
  |---|---|---|

No of sets = Number of lines / Set size

---

**Question**

* Cache size: 256 kB
* tag bits: 8
* 8 ways assocative

find byte addressable MM size?

**Solution**

We know 

* Cache size = No. of lines x line size

* No. of sets = No of lines / Set size

* Cache size = No. of sets x Set size x line size

* |8|x|y|
  |----|---|---|

* $$2^8 . 2^10 = 2^x . 2^3 . 2^y $$

* $$\frac{2^{18}}{2^3} = 2^x . 2^y $$
* $$2^{15} = 2^{x+y} $$
* $$x + y = 15$$

* PA split, 8 + x + y = 8 + 15 = 23
* MM size: 2^23 = 8 MB
