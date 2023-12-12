# Cache levels in CPU

generally CPU has three cache levels L1, L2 and L3

### Level 1 cache(L1)

* **Location**: L1 cache is the smallest and fastest cache, physically located on the CPU chip itself. L1 cache is genrally a SRAM.
* **Purpose**: It holds a small amount of both data and instruction that CPU is currently working with.

### Level 2 cache(L2)

* **Location**: L2 cache is larger then L1 and is located either on the CPU chip or very clost to it on the same die.
* **Purpose**: IT supplements the L1 cache by holding additional copies of data and instructions. L2 cache is larger but slower than L1.

### Level 3 cache(L3)

* **Location**: L3 cache, when present, is larger than both L1 and L2 and is shared among multiple CPU cores in a multi-core processor. It can be on the same chip or on a seprate chip(in case of multi-socket system).
* **Purpose**: L3 cache serves as a shared resources among multiple CPU cores, reducing contention for cache resources. It helps in enhancing overall system performance in multi-core processors. L3 is slower than the L1 and L2 cache.

$$HitRatio = \frac{No. of Hits}{No. of Hits + No. of Miss}$$

$$MissRatio = 1 - HitRatio$$

---

# Write allocation Vs No write allocation

|Sr. No.|Write allocation | No write allocation|
|---|---|---|
|1.| In the Write-allocate strategy, when a write operation is requested, the entire block containing the target address is first brought into the cache(if it is not already present)|In the no-write allocation stratergy, when a write operation is requested,the data is written directly to the main memory without bringing the corresponding cache block into the cache.|
|2.|The write operation is then performed on the cache copy of the block.|This approach is often used when it assumed that the data being written is unlikely to be read again soon or if the write-to-read ratio is low.|
|3.|This strategy is typical in systems where writing to the cache is relatively fast, and it is assumed that the data being written will likey be read again in the near future.|It avoids bringing unnecessary data into cache for write-only operation.|
||Example: Suppose a program writes to a specific memory location, and that location is not currently in the cache. With write-allocate, the entire cache block containing that location is fetched from main memory into the cache. The write is then performed on the cache copy.|Example: If a program writes to a specific memory location not currently in the cache and no-write allocation is in place, the data is directly written to the main memory, bypassing the cache. This can be advantageous if the data is unlikely to be read again in the near future.|

---

# Write through Vs Write Back

Write-through and write-back are two different cache write policies that determine how changes made to data in the cache, are propagated to the main memory

|Sr. no.|Write through|Write Back|
|---|---|---|
|1|In write through cache policy, every write operation to the cache is immidiately reflected in the main memory.|In a write-back cache policy, changes made to the cache are not immidiatley propogated to the main memory.|
|2.|After a write operation, both the cache line and corresponding location in main memory are updated simultaneously|The modified data is first written to the cache, and the corresponding location in main memory is updated only when the cache line is about to be replaced or when explicitly requested.|
|3.|This ensures that the data in the cache is always consistent with the data in the main-memory|This allows for multiple writes to the same location in the cache before updating the main-memory, potentially reducing memory traffic.|
|Write through policy is implementes when there is modification will perform in future.|Write back policy is implemented when in near future multiple modification is done on same cache line|
