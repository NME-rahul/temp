# Direct Mapping

* Direct memory mapping use many-to-one relationship, means many block can fill into the one specific cache line(this mapping do indexing)
* **Word:** Smallest addressable unit of memory.
  * Byte addressable: 1 Byte = 1 word

### Hardware Orgnization

**Working**: 
* When a address comes to the cache, The cache controller extracts the tag and offset bits ffrom the address.
* The comprators compare the tag bits of the addres with stored bits in each cache line.
* The outputs of all comprators are fed into OR gate and corresponding OR line's logic become HIGH, indicating cache hit.
  * If the OR output is LOW(cache miss), the data must be fetched from main memory.
* If there's a cache hit, the offset bits are fed into multiplexer. The multiplexer use these bits to select the specific byte within the matched cache line that need to retrieved.
* And then this correct fetched byte is sent to the processor.

|Circuit name|Size|No. of circuit required|Reason |
|---|---|---|---|
|comparator|$N$-bit comprator, where $N$ = Tag bits|1|due to each block have a particular line in cache to be map onto, regardless of cache size.|
|OR|$2^n$, where $n$: no of lines in cache|1|An OR gate is used to combine the outputs of multiple comparators, each checking the tag bits of a specific cache line.|
|Multiplexer|$2^{offset}-to-1$.|1|It selcts the specific byte within matched cache line|

### Physical address split

|Block Number|Block offset|
|---|---|

|Tag bits|Line/Index number|Block offset|
|---|---|---|

* **Block offset:** represents the word number of block.
* **Block Number:** represents the block number.
* **Tag bits:** tells the which block set is mapped into the cache memory.
* **Line/Index number:**(no. of lines) tells on which cache line a particular block of block set(reprsented in tag bits) is mapped.


---

<p align="center">
  <img alt="direct memory mapping" src="https://diveintosystems.org/book/C11-MemHierarchy/_images/DirectMapping.png" height="500" width="500" />
</p>

**Tag directory:** has as many entries as a cache lines have.

Tag directory size = No. of lines x No. of tag bits
 
