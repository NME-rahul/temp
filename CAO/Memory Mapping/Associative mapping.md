# Associative Mapping

* Associative mapping overcome the problem of conflict-miss in the direct memory mapping.
* A Block of main-memory can be mapped to any freely availabe cache line. This makes it fully associative mapping.
* It follows many-to-many relationship.

**Disadvantages:**
* At it took much time to search for block because data can be in any line of cache memory.
* It is expenisve from the point of hardare because it requires n-bit comprator where n is equal to tag bits.
  * 1 OR gate is also required.
  * Comprator size = tag bits = Line bits
  * No of comparator required = No. of lines in cache
 
$$Hit latency = T_{comparator} + T_{OR}$$

<p align="center">
 <img width="" alt="Screenshot 2024-01-05 at 2 15 14 PM" src="https://github.com/NME-rahul/temp/assets/100432854/5fb0f61d-f4c2-4fd1-9c7a-ca220ad78115">
</p>

**Why associative mapping?**
* In direct memory mapping policy we have strict rule to map a particular set of blocks to a fixed line of cache memory.
* And when we want to place another block in cache line it is not possible without replacing it, this is called conflict on direct mapping that's hy we use associative memory mapping.

**Physical Adrress bit split**

|Tag bits|Block offset|
|---|---|





