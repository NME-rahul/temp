# Secondary Key Indexing

* Indexing is done on primary key or any super key.
* Data must be ordered in index field.
* It can be dense or sparse index.

<p align="center">
  <img src="https://private-user-images.githubusercontent.com/100432854/285861405-20510311-67d2-4651-bf32-cd280c280ba4.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTEiLCJleHAiOjE3MDEwODgzMTksIm5iZiI6MTcwMTA4ODAxOSwicGF0aCI6Ii8xMDA0MzI4NTQvMjg1ODYxNDA1LTIwNTEwMzExLTY3ZDItNDY1MS1iZjMyLWNkMjgwYzI4MGJhNC5wbmc_WC1BbXotQWxnb3JpdGhtPUFXUzQtSE1BQy1TSEEyNTYmWC1BbXotQ3JlZGVudGlhbD1BS0lBSVdOSllBWDRDU1ZFSDUzQSUyRjIwMjMxMTI3JTJGdXMtZWFzdC0xJTJGczMlMkZhd3M0X3JlcXVlc3QmWC1BbXotRGF0ZT0yMDIzMTEyN1QxMjI2NTlaJlgtQW16LUV4cGlyZXM9MzAwJlgtQW16LVNpZ25hdHVyZT0yOTVmMzVkZGY0NzgzY2E2NTI1NDdlZTY2ZWM3OGQxYjQ3ZTRmYTI5NzY1MTJhODliNjkwZTgwZDBjYjA2MmExJlgtQW16LVNpZ25lZEhlYWRlcnM9aG9zdCZhY3Rvcl9pZD0wJmtleV9pZD0wJnJlcG9faWQ9MCJ9.nFMKtufrIl4E9WRZCJrarIRfXrq9n4WMmTnbQ4-9hoQ" height="500" width="600"/>
</p>


# Secondary Non-key Indexing

* Indexing is done non-key field.
* Data must not to be ordered on index field.
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
