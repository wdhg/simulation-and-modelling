# Discrete-Time Simulation

Given a state transition system (e.g. nodes with arcs) take \\( n \\) steps randomly throught the system, moving from one state to the next in each discrete step. There may or may not be a notion of time in the discrete steps made.

For example, consider a game of Monopoly where you want to find the probability of landing on each board position in the game. This can be done by starting at GO, simulating \\( n \\) dice rolls, following the rules of the game (including chance and community chest cards), and counting how many times each tile is landed on.

![](./images/monopoly.png)
