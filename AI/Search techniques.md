# Search Techniques

A search problem consists of 
* **State Space**: Set of all possible state where you can be.
* **Start State**: The state from where search begins.
* **Goal State**: A **Function** that looks at the current state returns whether or not it is the goal state.

> The solution to search problem is sequence of actions, called the plan that transforms the start state to the goal state. And this plan is acheived through search algorithms.

<p align="center">
  <img src="https://media.geeksforgeeks.org/wp-content/uploads/AI-algos-1-e1547043543151.png" height="" width="" />
</p>

## Uniformed

* This type search techniques are used where in the problem statement we have no information other then goal state and problem definition.
* This type of search is also called the blind search.
* These algorithms can only generate the successors and differentiate between the goal state and non-goal state.

### Breadth First search(BFS)

* **Stratergy**: BFS explores the search space level by level. It visits all nodes at current depth beforemoving on the nodes at the next level.
* **Data Structure**: BFS uses Queue data structure as it works on First-In-First-Out(FIFO).
* **Completeness**: BFS is complete and will find the soloution if it exists.
* **Memory Usage**: Requires more memeory compared to DFS as it needs to store informaion about all paths at a given depth.

**Eg.**

<p align="center">
  <img width="374" alt="tree" src="https://github.com/NME-rahul/temp/assets/100432854/5ffe0d2d-9bfa-4a53-bcd3-10d2d5c33b92">
</p>

**Solution**

<p align="center">
  <img width="374" alt="tree" src="https://github.com/NME-rahul/temp/assets/100432854/a102bb97-a7e9-4674-927c-0d82f23afb7c">
</p>


### Depth First search(DFS)

* **Stratergy**: DFS explores as deep as possible along each branch before backtracking. It goes deep into the search before moving to the next branch.
* **Data Structure**: Typically implemented using a stack(or recursion), as it works on Last-In-first-Out(LIFO).
* **Completenes**: DFS is not guranted to find the solution if state space is infinite. It may get stuck exploring a deep branch. The completness can be improved by introducing cycle count. 
* **Memory usage**: Requires less memory compared to BFS as it only needs to store inforamtion about one path.

**Solution**

<p align="center">
  <img width="374" alt="tree" src="https://github.com/NME-rahul/temp/assets/100432854/66fe6ae9-6b90-4882-8558-fd44bcfc4179">
</p>

**Ref**: https://www.geeksforgeeks.org/search-algorithms-in-ai/

