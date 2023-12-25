# Best First Search(BFS)

* Finds the shortest path in a graph or tree.
* Unlike Dijkastra's algorithm which prioirtize nods with minimum distance so far, BFS priortize nodes based on an estimated cost to reach goal. This estimated cost is called heruistic value.
* It can be implemented using priority queue or binary heap.
* NOTE: priority queue is a abstract data structure use binary heap to implmenet it.

**Algorithm**

    Pqueue(queue, front, rear)
      add starting node.
      for i=0 to n:
        remove front node
        add it's unvisited neighbours according to their priority
    
> Time Complexity: O(ElogV)

* At some points you will find that nodes with lower prioirty are placed before the higher ones at that step prioirty queue will fail, so use binary heap.

---

  <p align="center">
    <img src="https://github.com/NME-rahul/temp/assets/100432854/f92ea3dd-fa6b-477b-9f35-1c1236991f94" height="" width="" />
  </p>


We start from source “S” and search for goal “I” using given costs and Best First search.
 
* pq initially contains S
  * We remove S from pq and process unvisited neighbors of S to pq.
  * pq now contains {A, C, B} (C is put before B because C has lesser cost)
 
* We remove A from pq and process unvisited neighbors of A to pq.
  * pq now contains {C, B, E, D}
 
* We remove C from pq and process unvisited neighbors of C to pq.
  * pq now contains {B, H, E, D}
 
* We remove B from pq and process unvisited neighbors of B to pq.
  * pq now contains {H, E, D, F, G}

* We remove H from pq.  
* Since our goal “I” is a neighbor of H, we return.

