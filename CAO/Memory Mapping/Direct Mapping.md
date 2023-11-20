# Direct Mapping

* Direct memory mapping use many-to-one relationship, means many block can fill into the one specific cache line(this mapping do indexing)
* **Word:** Smallest addressable unit of memory.
  * Byte addressable: 1 Byte = 1 word


 
**Physical address split :**

|Block Number|Block offset|
|---|---|

|Tag bits|Line/Index number|Block offset|
|---|---|---|

* **Block offset:** represents the word number of block.
* **Block Number:** represents the block number.
* **Tag bits:** tells the which block set is mapped into the cache memory.
* **Line/Index number:** tells on which cache line a particular block of block set(reprsented in tag bits) is mapped.


---

<p align="center">
  <img alt="direct memory mapping" src="https://diveintosystems.org/book/C11-MemHierarchy/_images/DirectMapping.png" height="500" width="500" />
</p>

**Tag directory:** has as many entries as a cache lines have.

Tag directory size = No. of lines x No. of tag bits
 
