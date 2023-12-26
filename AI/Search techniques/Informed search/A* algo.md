# A* algorithm

* A* algorithm is used to find the shortest path between a starting and goal in a weighted graphs.
* It is a complete and optimal algorithm.

$$f(n) = g(n) + h(n) $$

is the function that determines the cost from current node to goal node, where
* g(n): actual cost
* h(n): heruistic cost

* **Necessary Conditions**
  * The heruistic value must be consistent, meaning h(n) <= g(n) => h(u) - h(v) <= g(u) - g(v)
  
#### Common heruistic function

1. **Manahatten distance:**
   $$d = |(x_2 - x_1)^2 + (y_2 - y_1)^2|$$
   
2. **Euclidian distance:**
   $$d = \sqrt{(x_2 - x_1)^2 + (y_2 - y_1)^2}$$
   
3. **Custome function:** Based on problem we can create our own heruistic function, for instance in a normal graph heruistic function can be the sum of vertics(u->k->v) to reach the vertice from u to v.

---

**Algorithm**

    unexplored_vertics = []
    explored_vertics = []
    AStar():
      for each node in unexplored_vertics:(start with starting node)
        for each child of node:
          if neighbour in unexplored:
            calculate the g(n) and h(n), and  f(n) = g(n) + h(n)
            keep track of the parent node to reconstruct the path
            add in explored_list


#### Applications

* Path finding in ames(eg. character movement, navigation)
* Route planning(eg. GPS navigation, logistics)
* Problem-solving in AI (eg. puzzle solving, planning)
* Network optimization

