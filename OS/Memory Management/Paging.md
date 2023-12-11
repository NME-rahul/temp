# Paging

* Each process is divided into equal size page and scattred/stored into the memory.
* A process is said to be loaded if all the pages are present in the memory.

* Page Table:
  
|Frame No./ Memory index|
|---|
|page 0 memory index|
|page 1 memory index|
|page 2 memory index|
|.|
|.|
|.|
|page n memory index|

* The index of the page table is used to determine the page no. of corresponding page.
* **Page Table entry size**: The number of bits require to store the frame addresss of a page that is stored in the memory.


## Address Translation


<p align="center">
  <img src="https://d3e8mc9t3dqxs7.cloudfront.net/wp-content/uploads/sites/11/2020/04/Hardware-Support-Block-diagram-for-Paging-in-Operating-System.png" height="" width=""/>
</p>


**Logical Addresss**

|Page No.|Offset|
|---|---|


**Physical/Memory Addresss**

|Frame No.|Offset|
|---|---|

* Take the offset of the logical address as it is.
* With help of page no./page table index no. present in logical address find the address of page from page table.
* Remember the page address gives the frame no./index number of memory.
