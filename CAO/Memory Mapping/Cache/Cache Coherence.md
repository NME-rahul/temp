# Cache Coherence

In multiprocessor environment when private(local) cache of individual cores are not synchronized with each other then, after performing operation indvidually by cores will produce and save differnet values of same variable this makes data inconsistent, called cache coherence.

It is ununiformity of shared resources data that ends up store in multiple local cache.

**Cache Coherence problem**: it is the challenge of keeping multiple local cache synchronized when one of processors updates it's local copy of shared data then it must reflect(share) it in other caches whose sharing data.

### Bits

1. **Modified bit**: For every cache line there is a "modfiy" bit that indicates the data exist in the line is modified by it's own processor thus it is inconsistent with main memory.

2. **Shared bit**: when a variable(data) stored in the line is in "shared" state means that the line contains unmodified data thus it can appear in at least of the CPU cache.

3. **Invalid bit**: Line data has been invalidated because some other processor wrote to their local copy that is shares with the current cache.

### Cache Coherence protocol

1. When a block of main-memory is fed into the processors private cache, state of the that particular line is set to shared.
2. If a processor decides to update that particular line's contnent then the line turrned "shared" to "modififed".
3. If other processor working on the same data modifies the data before current processor the state of current cache's line is demoted to "invalid".

