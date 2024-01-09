  # Hill Climmbing

  * It is a optimzation technique.
  * It iteratively moves towards the direction of increasing elevation(or decreasing cost) in the search space.
  * It uses greedy approach.
  * It is not a complete algorithm, means it give optimal solution at minimumt time.

> Time Complexity: O(n)

**Pseudo Code**

    Inititial_state = array[0]

    if initial_state = goal_state:
      return initial_state
    else:
      current_state = initial_state

    for i=0 to i < current state's neighbour:
      present_state = current_state[i]
      if present_state = goal_state:
        return present_state
      if present state is better then current state:
        current_state = present_state

<p align="center">
  <img src="https://github.com/NME-rahul/temp/assets/100432854/48d3f101-2a27-43a2-8b34-b12298634d5f" width="" hight="" />
</p>
