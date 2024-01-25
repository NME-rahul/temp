# Secondary Key Indexing

* Indexing is done on primary key or any super key attribute.
* Data must be unordered in index field.
* It can be dense or sparse index.

<p align="center">
  <img src="https://private-user-images.githubusercontent.com/100432854/285861405-20510311-67d2-4651-bf32-cd280c280ba4.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MDYxOTU1MDIsIm5iZiI6MTcwNjE5NTIwMiwicGF0aCI6Ii8xMDA0MzI4NTQvMjg1ODYxNDA1LTIwNTEwMzExLTY3ZDItNDY1MS1iZjMyLWNkMjgwYzI4MGJhNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBVkNPRFlMU0E1M1BRSzRaQSUyRjIwMjQwMTI1JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDI0MDEyNVQxNTA2NDJaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT00YTE2ZDE4NmY1N2I1NTQ4NWQyNzIzM2MzNzI4YjhiZWY2YTQzMjQ3Yzg3YmMwOWMyZTlkNjM2NGUyMTdlYTVmJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.4stLC7Paw_j3dzZjm_bfxmcByEO0jwIfTbfrCUEb8kA" height="500" width="600"/>
</p>


# Secondary Non-key Indexing

* Indexing is done non-key field.
* Data must be unordered on index field.
* It is a two level Indexing.
 
<p align="center">
  <img src="https://www.guru99.com/images/1/070119_0833_IndexinginD4.png" height="" width=""/>
</p>

**Explanation**

* There is two level indexing.
* We performs indexing on unorderd non-key field.
* The first level indexing is ordered dense indexing that that contains a record pointer and coresspoding Non-key field.
* The record pointer points to every index where it is present.
* Beacuse the first level indexing is ordered, in second level we only points to the first record of block.
