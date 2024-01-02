# Segmentation

* Each process id divided into unequal size of segments.
* A process is said to be load if all the segments were present in the memory.

* Segment Table:
 
|Length of segment|Frame index/No.(base address of memory)|
|---|---|
|100|segment 0 memory index|
|400|segment 1 memory index|
|300|segment 2 memory index|
|.|.|
|.|.|
|.|.|
|733|segment n memory index|

* The index no. of segment table is used to determine segement no. of corresponding segment.

# Address transaltion
<p align="center">
  <img src="https://binaryterms.com/wp-content/uploads/2021/01/Segment-table-Segmentation-in-os.jpg" height="" width=""/>
</p>


* **Logical Address**

  |Segment No.|Offset|
  |---|---|

* **Physical Address**

  |segment memory index|Offset|
  |---|---|

* First, compare the legnth/limit of offset of logical address with the coreponding segment offset limit.
* If yes, then take out the segment memory index with the help of segemnet no. of logical address.
* Else, discard the logical adress(Invalid address).
