# Types of cache misses
1. compulsory miss
2. Conflict miss
3. Capacity miss

### 1. Compilsory Misss

### 2. Conflict miss

When a an cache block is thrown out for another block and if that thrown out block is accessed again then it is called conflict miss.

### 3. Capacity miss

 When the working set size is larger then the cache lines then this type of cache miss happens. When cache lines are filled to cacpicty and a new block is refrenced then any one block has to evicate from cache to create space for new block.


 ## Coherenc miss

A coherence miss occurs when one processor updates a data item in its private cache, making the corresponding data item in another processor’s cache stale.  When the second processor accesses the stale data, a cache miss occurs
