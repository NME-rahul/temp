# Memory Mapping

* Memory mapping is always done in Round-robin fashion.
* let, $n^{th}$ block of memory need to be map onto the cache memory and there are $m$ line in the cache, then $n^{th}$ % $m$ will be the line where the memory will take place.
* In case of set associaitve mapping $n^{th}$ % $m$.
  * where $m$ is the no of sets in the cache
* In case of fully associative a block can be place in any cache line and if cache is full then page replacement policy is used to evict a page to make room free for next page.

  $$HitLatency = T_{comprator} + T_{OR}$$

* comprators and or gate works parallely so take 1 OR gate 1 comprators latency.
* DATC(Data Access Time of Cache): Data retrival time

  $$DATC = HitLatency + T_{multiplexers}$$
