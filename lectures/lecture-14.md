# Search Strategies and Applications

## Search Problems

We can find the way from A to B by doing a random walk, &epsilon; = 1, on the map. Q-learning, &epsilon; < 1, is also essentially a random walk until the goal is found. But _navigators_ use something much more efficient.

## Graph Problem

A graph problem (or path-finding problem) consists of:

- A set of **nodes**
- A set of **edges** between nodes
  - These may be labelled with actions and/or costs
- A node called **start node**
- A set of nodes called **goal nodes**

The **solution** to a graph problem is a path, i.e. a sequence of states, leading from the start node to a goal node.

## Generic Search Algorithm: Frontier

Given a graph and a start node, we want to explore paths from the start to the goal node. We define a generic algorithm for solving graph problems, where the algorithm maintains a set of paths called **Frontier** (or Fringe). Any solution must begin with a path that belongs to the Frontier.

### Instances

One way of implementing the Generic Search Algorithm is to let the Frontier be a list, and always select the first path (head) of the list. The paths in the Frontier can be ordered according to different policies:

- **Breadth-first search:** New paths are inserted at the end of the list. Then the Frontier is an ordinary queue, i.e. a First-in First-Out (FIFO) queue.
- **Depth-first search:** New paths are inserted at the front of the list. Then the Frontier is a stack, i.e. a Last-in First-Out (LIFO) queue.
- **Best-first search:** New paths are inserted into the list based on their _"grades"_. The Frontier is always sorted by _"grades"_.

### Breadth-first Search (BFS)

It always finds a solution if there is one, and it will always finds the shortest solution since it goes through every possible solution. But the search then requires a lot of memory for storing all paths down to depth _n_.

### Depth-first Search (DFS)

It's not guaranteed to find the path with fewest arcs. The search is appropriate when the search space is small or when many solutions exist. It's no appropriate when it can get trapped in infinite paths that can happen if the graph is infinite or contains loops.

### Iterative Deepening DFS

1. Do a depth-first search down to depth 1, so only paths of max length are put into the Frontier.
2. If that does not lead to a solution, do a depth-first search down to depth 2.
3. If that does not lead to a solution, do a depth-first search down to depth 3.
4. Repeat this until a solution is found.

**Advantages:**

- Always finds a solution if there is one
- Always finds the shortest solution
- Memory efficient

**Disadvantages:**

- Some nodes are revisited many times

### Adding Arc Costs

Sometimes it's useful to put costs on arcs, for example the costs might represent time or distance. We write the cost of an arc `(ni, nj)` as `cost(ni, nj)`.

Given a path `p = (n0, n1, ..., nk)`, the `cost(p)` is defined as the _sum of the costs of the arcs appearing in p_. Given a cost function, we may look for an optimal solution to a graph problem, i.e. the shortest or fastest path.

### Lowest-cost-first Search (LCFS)

It applies when the arcs are labeled with costs, and is a version of the Generic Search Algorithm. Lowest-cost-first search lets the Frontier be a list sorted by path cost, with the lowest cost path first.

When arc costs are all equal, i coincides with Breadth-first search. It always finds the cheapest solution but has limited scalability (same that applies for Breadth-first search).

## Informed Search

Used when we want to take in additional parameters or features about the environment.

### Heuristics

A **heuristic function** is a functio _h_ that assigns a non-negative real number `h(p)`to each path _p_. Intuitively it's an estimate of the cost of the cheapest path from end-node of _p_ to a goal node.

For calculating `h(p) the only relevant part of _p_ is its end-node. Some texts define heuristic functions on nodes and costs on paths. Our choice here is to define both heuristic functions and costs on paths.

### Greedy-best-first Search (GBFS)

### A\* Search Algorithm

A\* (A-star) is a very powerful search algorithm that is a mix between lowest-cost-first and best-first search.

A\* uses both path costs and heuristic values, where `cost(p)` is the cost of path _p_ and `h(p)`estimates the cost from the end node of _p_ to a goal. `f(p) = cost(p) + h(p)` is the estimation of the total path cost of going from the start node, via path _p_, to a goal.
