# Dijkastra and negative weight edges

* Dijkastra can luckicly work with negative edges otherwise never.
* if all edges are negative then dijasktra will work without any problem.
* It can not even detect negative weight like bellmen-ford.


## Effect of changing edge weight on MST and Shortest path

|Action|MST | Shortest Path|
|---|---|---|
|Add some weight| No Change | Change |
|Subtract|No Change| Change|
|Multiply|No Change|Change|
|Power|No Change|Change|
