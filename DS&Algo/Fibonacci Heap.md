# Fibonacci Heap

## Motivation
A standard Binary Heap performs key decrease operation in logarithmic time, Fibonacci heap achieves it in O(1) amortized time for `Decrease-kye`, `Insert`, `Find-min`, and `Union`. This makes them theortically optmal for graph algorithms like Dijkstra's single-source shortest path and prim's minimum spanning tree.


# Structure
A Fibonacci heap is a collection of min-heap-ordered trees(a forest).

* Min-Heap property: The smallest element is always at the root of one of the trees.
* Consolidated Root list: All roots ae linked together in a doubly circular linked list.
* Pointer to minimum: The heap maintains a pointer directly to the root with the overall minimum key.
* 
