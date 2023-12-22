# Adversarial search

* As the name suggest this technique is applied when there is two agents are fighting and minimizing the other ones probability to get higher reward.
* Moves played by agents should be alternate.
* Using dice is not involved.
* geerally these techniques are applicable in games this is why they are also called game playing algorithms.
* Fully observable environments.
* Min-Max algo. uses both top-down and bottom-up approach.

---

## Mini-Max algorithm
* It aims to find the optimal move for a player by assuming their oponent will also play optimal move.
* It works by exloring possible future game states and evaluating to determine the best course of action.

**Game Representation**:
* Each node represents a game state.
* Branches reprsents possible moves from the state.
* Leaf nodes represents terminal state.

**stratergy**:

* **Max**: Increase the chance of wining the game.
* **Min**: Try to decrease the chance of Max to win.

  <p align="center">
    <img src="https://github.com/NME-rahul/temp/assets/100432854/48fc5c0c-db4c-4f25-935e-4b915dc69f65" height="" width="">
  </p>
  
**Algo.**

      minimax(node, depth, maximizingPlayer):
        if node == terminal or depth == 0:
          return cost of node branch
          
        if maximizingPlayer is True:
          for each child of node:
            value = minimax(child, depth-1, False)
            bestValue = max(value, bestValue)
          return bestValue

        if maximizingPlayer is False:
          for each child of node:
            value = minimax(child, depth-1, True)
            bestValue = min(value, bestValue)
          return bestValue
            
            
> Time Complexty: O(b^d)

* b: branching factor(average moves at each level).
* d: depth of tree.
