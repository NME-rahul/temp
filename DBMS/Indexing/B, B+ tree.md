# B tree

* It is a data strcture generaly used to store large amount of data.

* It is a balanced tree.
* If the B tree is of order m then the tree have m number of pointer(search key) and m-1 number of keys(data/value).
* Block size = Node = m + (m-1)

  <p align="center">
    <img src="https://vitalflux.com/wp-content/uploads/2015/05/btree-order5.jpg" height="300" width=""/>
  </p>


# B+ tree

* B+ tree is a variant of the B tree.
* B+ can max m-1 keys and min m/2 - 1 keyscan be stored in cache.
* In B+ ree records are store only be kept in leaf nodes.
* To make search queries more efficicet, the leaf nodes of the B+ tree in the data structure are connented together in form of singly link list.
* B+ trees are used to store vast amounts of data that are too loarge fir in MM.
* The internal nodes are stored in memory, wheras leaf nodes are placed in the secondary memory.
* B+'s internal nodes are often referred as index nodes.

**Advantages**

* B+ tree require equal number of disc accesses as B tree.
* B+ tree has lower hwight the B tree.
* indexing is done via internal keys.
* Because the data is store on leaf nodes, search queries are faster.
  
**Internal Node**

* A B+ tree have minimum n/2 record pointers in internal node.

**Leaf Node**

* In B+ tree the data is only stored in leaves.
* Leaf node keeps the copy of every parent nodes key.
* Leaf nodes are connected through a link list structure.


  <p align="center">
    <img src="https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1608912327-.png" height="300" width=""/>
  </p>
