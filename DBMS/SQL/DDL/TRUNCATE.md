
# TRUNCATE

* It works same as delete but it delete all rows because we can not use WHERE calsue with it.
* It also aintains realtion as DELETE command
* TRUNCATE Command first locks every table and then delete. that's why it is faster then DELETE
* whereas DELETE command locks row by row and delete that's why it is slower then TRUNCATE.
