# Path_Finding

An implementation of A* algorithm to find the shortest path between two points in a given space, which simulates a simplified version of challenges faced in robotics navigation and manufacturing automation.


A* algorithm can be seen as an extention of Dijkstra with heuristics. This project used following heuristic function:

$$  h(u) = \text{w}(u) + \text{distance}(s, u) + \text{distance}(u, e)$$

where, 
- $u$ is current point, $s$ is the start point, $e$ is the end point;
- $\text{w}(u)$ is the weight of point $u$;
- $\text{distance}(\cdot,\cdot)$ calculates the distance between 2 points. It can be chosen according to the task, here, since the agent can only move in 4 directions (up, down, left, right), I used the __Manhattan distance__.

It is easy to prove that $h(u)$ is not larger than the actual cost for the journy $ s \rightarrow u \rightarrow e$. Hence, we can use this value as the heuristic value and ensure the found path is feasible.

On the other hand, __genetic algorithm__ (GA) can also be used to solve Path Planning Problem, but not so suitable for the specific task.

I tried GA, but since the small scale map and other simple constraints, GA cannot improve the performance.

E.g., in population initialize stage, it's almost impossible to generate a large enough population, i.e., it can only generate a few number of feasible DNA.
