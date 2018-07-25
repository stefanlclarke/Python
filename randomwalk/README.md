A random walk on a 5x5 grid, displayed in pygame, with the aim of reaching the green square.
I use MonteCarlo reinforcement learning to solve this problem.
There is a 5x5 matrix, W, for which each entry is a vector of 2, 3, or 4 dimensions depending on how many possible moves there are from that space on the grid.
The first entry in each vector corresponds to moving up, then left, then down, then right.
From the current position of the dot it follows the path of maximum entry in this vector with probability 1 - epsilon, and moves randomly with probability epsilon (epsilon greedy policy evaluation).
Epsilon decays as the machine explores more routes.
Once the machine reaches the green square, it updates W as follows:
  Work backwards along the path, considering each tile visited in reverse order.
  For each tile, let l be the number of steps between visiting this tile and reaching the green square.
  if w is the weight in the vector corresponding to the action that the dot took from this tile (direction moved in) then mu*l is added to    w.
This algorithm runs a set number of iterations, which you can declare in the function.
There is a scatter graph showing it's rate of convergence in the ipynb file. 300 attempts is more than enough for it to find the correct path by Montecarlo evaluation.
