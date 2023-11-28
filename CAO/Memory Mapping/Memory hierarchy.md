* Dynamic memory is slower then the static memory
* cache is High-speed Static RAM(SRAM).

# Cache levels in CPU

generally CPU has three cache levels L1, L2 and L3

### Level 1 cache(L1)

* **Location**: L1 cache is the smallest and fastest cache, physically located on the CPU chip itself.
* **Purpose**: It holds a small amount of both data and instruction that CPU is currently working with.

### Level 2 cache(L2)

* **Location**: L2 cache is larger then L1 and is located either on the CPU chip or very clost to it on the same die.
* **Purpose**: IT supplements the L1 cache by holding additional copies of data and instructions. L2 cache is larger but slower than L1.

### Level 3 cache(L3)

* **Location**: L3 cache, when present, is larger than both L1 and L2 and is shared among multiple CPU cores in a multi-core processor. It can be on the same chip or on a seprate chip(in case of multi-socket system).
* **Purpose**: L3 cache serves as a shared resources among multiple CPU cores, reducing contention for cache resources. It helps in enhancing overall system performance in multi-core processors. L3 is slower than the L1 and L2 cache.

$$HitRatio = \frac{No. of Hits}{No. of Hits + No. of Miss}$$

$$MissRatio = 1 - HitRatio$$
