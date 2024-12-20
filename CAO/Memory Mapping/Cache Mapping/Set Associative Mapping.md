# Set Associative Mapping

* Set associative mapping combines the best of direct and associative cache mapping.
* In this technique cache is divided into set of lines, by dividing cache the block can take place in any line of set this provides the flexibility of associative mapping.
* By creating sets in cache memory the number of conflict misses reduces because if a line of a particular set is accomodated by a block then new block can accomodate other line of same set.

### Hardware Orgnization

* When an address comes to cache memory, the cache contoller extracts the tag and set and offset bits.
* The number of select in each multiplxer should be equal to the set bits to read set number.
* Multiplexers(no of input lines = no. of sets) inputs has the sets inside the cache memory that are selceted by the select line.
* Then within set, comparator compares the tag bits with each cache line stored inside that the set.
* If it thare is match then the the output of comparator is fed into the OR gate, to make output of OR gate HIGH indicating cache hit.
  * If the output of OR gate is LOW indicating cache Miss.
* After selecting the cache line the multiplexer is used to select the word within the line.

|Circuit Name|Size|No of circuits required|Reason|
|---|---|---|---|
|Comaprator|$N$-bit comparator, where $N$ = no of tag bits|set size|the comparator compares the tag bits within a set, if we have $k$-way set associative memory then we require $k$ number of comparators.|
|OR|$2^n$ where $n$:set size, is the number of lines in a set||the output of comparator is fed into the OR gate, that means we require a OR that has input equal to the number of lines per set.|
|Multiplexer 1|$2^{k}-to-1$, where $2^k$: no. of sets in cache||It selects the Set.|
|Multiplexer 2|$2^{offsetBits}-to-1$||It selects the Set and also selcets the particular word within cache line, so if a line contains 64 word then we need $\log_2(64)-to-1$ mulitplexer. |

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
