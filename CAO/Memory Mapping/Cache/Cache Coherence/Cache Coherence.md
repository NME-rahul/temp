# Cache Coherence

In multiprocessor environment when private(local) cache of individual cores are not synchronized with each other then, after performing operation indvidually by cores will produce and save differnet values of same variable this makes data inconsistent, called cache coherence.

It is ununiformity of shared resources data that ends up store in multiple local cache.

**Cache Coherence problem**: it is the challenge of keeping multiple local cache synchronized when one of processors updates it's local copy of shared data then it must reflect(share) it in other caches whose sharing data.

### States of cache lines

1. **Modified**: For every cache line there is a "modfiy" bit that indicates the data exist in the line is modified by it's own processor thus it is inconsistent with main memory.

2. **Shared**: when a variable(data) stored in the line is in "shared" state means that the line contains unmodified data thus it can appear in at least of the CPU cache.

3. **Invalid**: Line data has been invalidated because some other processor wrote to their local copy that is shares with the current cache.

### Cache Coherence protocol

1. When a block of main-memory is fed into the processors private cache, state of the that particular line is set to shared.
2. If a processor decides to update that particular line's contnent then the line turrned "shared" to "modififed".
3. If other processor working on the same data modifies the data before current processor the state of current cache's line is demoted to "invalid".

### Other States of cache lines

4. **Exclusive**: Cache line is present only in the current cache and data of line matche with main-memory data. it may change to shared state at any time in response to **read request** from any other processor.

5. **Owned**: The cache blocks will owne by the particular processor's cache only and **read request** by other processor will grant only by the choice of current cache.

6. **Forward**: In multiprocessor if contnet of a line is updated by current processor then it is current processor's responsibilty to forward the updation to all other processors who are working on the same data.
