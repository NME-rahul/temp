# Set Associative Mapping

* Set associative mapping combines the best of direct and associative cache mapping.
* In this technique cache is divided into set of lines, by dividing cache the block can take place in any line of set this provides the flexibility of associative mapping.
* By creating sets in cache memory the number of conflict misses reduces because if a line of a particular set is accomodated by a block then new block can accomodate other line of same set.
* Number of Comparater required = Set size
* N-bit Comparater required, where N = tag bits

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
