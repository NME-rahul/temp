# Locality of References

It referes to a phenomenon in which a computer program tends to access same set of memory locations for a particular time period. in other words Locality of Reference refers to he tendency of the computer program to acces instruction whose addresses are near one another.


1. First way is that CPU should fetch the required data or instruction and use it, when the same data or instruction is required again, CPU again has to aaccess the same main memory location for it and we already know that main memory is the slow to access.

3. The second way is to store the data or instruction in the cache memory so that if it is needed soon again in near future it could be fetch in much faster way.


### Cache Oeprations

It is based on the principle of locality of references. There are two ways, in which data or instruction is fetched from main memory and get stored in cache memeory.

**1. Temporal Locality** - Temporal locality means current data or instruction that is being fetched may be needed son. So we should store that data or instruction in the cache memory to avoid repeated access of main memory.

**2. Spatial Locality** - Spatiality means instruction or data near to the current memory location that is being fetched, may be needed soon in the near future.


Here, we are talking about nearly located memory location while in temporal locality we were talking about the actual location that was being fetched. 
