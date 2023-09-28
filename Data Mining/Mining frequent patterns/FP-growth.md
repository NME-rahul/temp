## FP-growth tree

#### Algorithm:

1. Identify frequent items
	* fom given transaction database, identify unique items and listout them.
	* Now count each item's frequency in each transaction.
	* Sort the item list in descending order.
	* by given minimum-support(minimum frequency count to be a support item), identify and list the items having count greater or equal to the minimim-support with their count.
	
2. Construct the tree
	* mark the root node as NULL.
	* from each transaction remove items that does not have count grater or equal to the minimum support.
	* now in remaining transaction instance, we have only those items which have count greater and equal to min.support.
	* trace out each items transaction by transaction and update their count to construct tree.
3. find frequnt itemset
	* now we have tree of most frequrnt items.
	* from these use combination to create frequent-itemset.



eg.

|Transaction ID|Items|
|---|---|
|T1| {Hotdogs, Buns, Ketchup}|
|T2| {Hotdogs, Buns}|
|T3| {Hotdogs, Coks, Chips}|
|T4| {Coks, Chips}|
|T5| {Coks, Ketchup}|
|T6| {Hotdogs, Coks, Chips}|

1. Identify unique items and their count

|Unique Items|Frequncy|
|---|---|
|Hotdogs| 4|
|Buns|2|
|Ketchup|2|
|Coke|3|
|Chips|4|

2. Sort the list in descending order

|Unique Items|Frequncy|
|---|---|
|Hotdogs| 4|
|Chips|4|
|Coke|3|
|Buns|2|
|Ketchup|2|

3. Most frequnt items that have frequency greate or equa to min. support

      {Hotdogs: 4, Chips: 4, Coke: 3, Buns: 2, Ketchup: 2}

4. Now Cearte the ordered itemset by eleminating items having frequency count lower then min. support.

|Transaction ID|Items|Ordered-itemset|
|---|---|---|
|T1| {Hotdogs, Buns, Ketchup}| {Hotdogs}|
|T2| {Hotdogs, Buns}| {Hotdogs}|
|T3| {Hotdogs, Coks, Chips}| {Hotdogs, Chips, Coke}|
|T4| {Coks, Chips}| {Coke, Chips}|
|T5| {Coks, Ketchup}| {Chips}|
|T6| {Hotdogs, Coks, Chips}| {Hotdogs, Chips, Coke}|

5. now construct the FP tree by tracing out each transaction, Mark first node  as NULL.

<img width="1406" alt="Screenshot 2023-09-25 at 7 44 56 PM" src="https://github.com/NME-rahul/Artificial-Neural-Network/assets/100432854/7ac26299-6ddd-449f-8765-49453b4b5cb1">

6. Now from reverse

|Items|Conditional pattern base|
|---|---|
|Coke| {Hotdogs, Chips: 2}|
|Chips| {Hotdogd:4}, {Coke:1}|
|Hotdogs| |

7. from above make Condition frequent table and find common items in every condition-itemset


|Items|Common items|
|---|---|
|Coke| {Hotdogs, Chips: 2}|
|Chips| No common in both set|
|Hotdogs| empty |

8. so from above common itemset, make combination with each item to generate frequnt itemset

      {(Coke, Hotdogs: 2), (Coke, Chips: 2), (Hotdogs, Coke, Chips: 2)}
  
      
  
