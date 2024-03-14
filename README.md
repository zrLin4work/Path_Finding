# Overview

An implementation of A* algorithm to find the shortest path between two points in a given space, which simulates a simplified version of challenges faced in robotics navigation and manufacturing automation.


A* algorithm can be seen as an extention of Dijkstra with heuristics. This project used following heuristic function:


$$  h(u) = \text{w}(u) + \text{distance}(s, u) + \text{distance}(u, e) + \text{min}\{\text{w}(v)|v \in\text{NextStep}(u) \}  + \text{RestObstacles}(u)$$

where, 
- $u$ is current point, $s$ is the start point, $e$ is the end point;
- $\text{w}(u)$ is the weight of point $u$;
- $\text{distance}(\cdot,\cdot)$ calculates the distance between 2 points. It can be chosen according to the task, here, since the agent can only move in 4 directions (up, down, left, right), I used the __Manhattan distance__.
- $\text{min}\{\text{w}(v)|v \in\text{NextStep}(u) \}$ get the minimum cost of all possible next step choices for point $u$, i.e., if we choose point $u$, no matter who is $u$'s successor, its is no smaller than this value. 
- $\text{RestObstacles}(u)$ count the rest obstacles in the subgraph that bounded by point $u$ and the end point $e$. More obstacles remain, more likely to detour. 


I tried GA, but since the small scale map and other simple constraints, GA cannot improve the performance.

E.g., in population initialize stage, it's almost impossible to generate a large enough population, i.e., it can only generate a few number of feasible DNA.

# Instructions

To run the algorithm, can choose to use the Jupyter Notebook or Google Colab.

More detailed description of each class and function can be found in the file.

# Requests

All parts of the algorithm is implemented by hand, so it only relies on some basic libraries.
