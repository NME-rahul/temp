# Alpha-Beta Pruning

* It is an optimization technique for the mini-max algorithm.
* It cuts-off branches of tree which need not to be searched because there is already available a better move.

* **Alpha**: (intially -INF)It is the best value that the maximizer curently can gurantee at that level or above.

* **Beta**: (initially +INF)It is the best value that minimizer currently can gurantee at that level or below.

---

**Pseudo code**

    MiniMax(node, depth, maxPlayer, alpha, beta):

      if node == leaf :
        return value of node

      if maxPlayer:
        bestValue = -INF
        for each child node:
          value = MiniMax(child, depth-1, False, alpha, beta)
          bestValue = max(value, bestValue)
          alpha = max(bestValue, alpha)
          if alpha >= beta:
            break
        return bestValue

      if not maxPlayer:
        bestValue = +INF
        for each child node:
          value = MiniMax(child, depth-1, True, alpha, beta)
          bestValue = min(value, bestValue)
          beta = min(bestValue, beta)
          if alpha >= beta:
            break
        return bestValue

> Time Complexity: O(b^d/2)


<p align="center">
    <img src="https://github.com/NME-rahul/temp/assets/100432854/624c585c-1c61-4f41-b74b-3e99ad71a941" height="" width="">
</p>

---

**Iteration 1**:

On right side level 3,

min node
    
    value = MiniMax(child=3, depth=4-1, maxPlayer=True, alpha=+INF, beta=-INF) = 3
    bestValue = min(value, bestValue) = min(3, +INF) = 3
    beta  = min(bestValue, beta) = min(3, +INF) = 3

**Iteration 2**:

max node

    value = MiniMax(child, depth=3-1, maxPlayer=False, alpha=+INF, beta=3)
    bestValue = max(3, -INF) = 3
    alpha = max(3, -INF) = 3


**Iteration 3**:

min node

    value = value = MiniMax(child, depth=2-1, maxPlayer=False, alpha=+INF, beta=3)
    bestValue = min(3, +INF) = 3
    beta = min(3, +INF) = 3

**Iteration 4**:

min node

    value = MiniMax(child, depth=2-1, maxPlayer=False, alpha=+INF, beta=3)
    bestValue = max(3, -INF) = 3
    beta = max(3, -INF) = 3
