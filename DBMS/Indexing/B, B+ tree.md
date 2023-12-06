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
* In B+ tree the data is only stored in leaves.
* Leaf node keeps the copy of every parent nodes key.
* Leaf nodes are connected through a link list structure.

  <p align="center">
    <img src="https://s3.ap-south-1.amazonaws.com/s3.studytonight.com/tutorials/uploads/pictures/1608912327-.png" height="300" width=""/>
  </p>
