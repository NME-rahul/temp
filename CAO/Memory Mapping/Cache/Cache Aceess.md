## Physically Indexed and Physically Tagged cache
Data is checked in cache by using the tag and index/set bits. Such cache where the tag and index bits are generated from physica address is called Phyiscally Inedxd Physically Tagged(PIPT) cache.

By default it is used

Average Memeory acess time = Hit time + Miss rate * Miss penalty

<div align="center">
  <img height="" width="" src="https://github.com/user-attachments/assets/988a328d-f2b2-4044-83aa-047b446965fa" />
</div>

**Disadvanteges: -**

1. This processs is quite sequential.
2. TLB is accesses every beore accessing TLB to convert virtual address to physical address.

## Virtually Indexed and Virtually Tagged cache


## Virtually Indexed and Physically Tagged cache
Indexing the cache is an expesive operation, so it is desireable to overlap indexing with TLB looplup(faster than PIPT cache).
VIPT cahce uses tag bits from physical address and index from virtual address. The cache is searched using the virutal address and tag part of physical address is obtained. The TLB is searched paralley with virtuall address, and physicall address is obtained. Fianlly, the tag part of physical address obtained from VIPT cache is compared with physicall address's tag obtained from TLB. If they both are same, then it is cache hit else miss.

Hit time = max(cache hit time, TLB hit time)
usually Hit time = cache hit time because due to very small size of TLB

<div align="center">
  <img height="" width="" src="https://github.com/user-attachments/assets/34a27a2f-827f-4829-b46b-ae6dc8b63b49" />
</div>

**Aliasing:**

When multiple virtual addresses from the same address space migh map to same physical address but we do virtual access to the cache these addresses ende up in the difference place in cache.

**Advanteges: -**
* There is no need to flush the cache during contex switch because we wha we find in cache is checked against the physcial address.
