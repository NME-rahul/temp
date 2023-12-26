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

---

**Question**

|   |0  |1  |2  |3  |4  |5  |
|---|---|---|---|---|---|---|
|0  |S  |-  |-  |-  |-  |-  |
|1  |-  |x  |x  |-  |x  |-  |
|2  |-  |-  |-  |-  |x  |-  |
|3  |-  |x  |-  |-  |-  |-  |
|4  |-  |-  |x  |-  |x  |-  |
|5  |-  |-  |-  |-  |G  |-  |

* x denotes the hurdles and - clear path.
* Assume the character can move in four directions up, down, left and right.
* The cost of movement is 1.
* The heruistic function is manhatten distance.
* Find the shortest path.
* Note: heruistic value is estimated value so while calculating h(n) ignore hurdles.

**Solution**

Algorithm:

    def manhatten_distance(X, Y):
      return abs((X[1]- X[0]) + (Y[1] - Y[0]))

    def function(unexplored_node, neighbours, cordinates):
      explored_nodes = []
      save_nodes = []

      for i, node in enumerate(unexplored_nodes):
        (x2, x1) = cordinates[i]
        save_neighbour = {'cordinates': [], 'cost': []}
        for j, neighbour in enumerate(node): #up, down, left, right
          if neighbour in explored_nodes:
            continue
          (y2, y1)  = cordinates[j]
          if x2 < 0 or x1 < 0 or y2 < 0 or y1 < 0:
            continue
          actual_cost = 1 #always, given
          estimate_cost = manhatten_distance((x2, x1), (y2, y1))
          if actual_cost >= estimate_cost:
            total_cost = actual_cost + estimate_cost
            save_neighbour['cost'].append(total_cost)
            save_neighbour['cordinates'].append(total_cost)
         explored_nodes.append(neighbour)
         neighbour =  save_path_cost.index(min(save_neighbour['cost'])])
         save_nodes.append(save_neighbour['cordinates'][neighbour])

* Iterration 1: start from S
  * find the cordinates of neighbours of S, remove negative cordinates(for this problem, because negative cordiates are not in state set).
    
        for i, node in enumerate(unexplored_nodes):
          (x2, x1) = cordinates[i]
    
  * (x2, x1) = (0,0)

        for j, neighbour in enumerate(node): #up, down, left, right
          if neighbour in explored_nodes:
            continue
          (y2, y1)  = cordinates[j]
    
  * (y2, y1) = (0, 1), (1, 1), (1, 0)

        actual_cost = 1 #always, given
        estimate_cost = manhatten_distance((x2, x1), (y2, y1))
 
  * (0, 1) => | (0-0) + (1-0)| = 1, (1, 1) => | (1-0) + (1-0)| = 2, (1, 0) => | (1-0) + (0-0)| = 1
 
        if actual_cost >= estimate_cost:
            total_cost = actual_cost + estimate_cost
            save_neighbour['cost'].append(total_cost)
            save_neighbour['cordinates'].append(total_cost)
         explored_nodes.append(neighbour)
         neighbour =  save_path_cost.index(min(save_neighbour['cost'])])
         save_nodes.append(save_neighbour['cordinates'][neighbour])

   * (1, 1) violates the condition actual_cost = 1 and heruistic = 2

           total_cost = actual_cost + estimate_cost
           save_neighbour['cost'].append(total_cost)
           save_neighbour['cordinates'].append(total_cost)
         explored_nodes.append(neighbour)
         neighbour =  save_path_cost.index(min(save_neighbour['cost'])])
         save_nodes.append(save_neighbour['cordinates'][neighbour])

   * actual_cost = actual_cost + estimate_cost = 1 + 1 = 2
   * here, save_neighbour['cost'] = [2, 2], save_neighbour['cordinates'] = [(0, 1), (1, 0)]
   * (0,1) and (1,0) have the same disance so min function will choose first cordinate in the list.
   * saved_node = [(0,1)]

* repeat this process for ever node until you reach to goal node.
