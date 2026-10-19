---
layout: page
parent: Project 3
title: Planning in Michigan
nav_order: 1
---

# Planning in Michigan (In Code)
{: .no_toc }
{: .fs-6 .fw-300 }

## Instructions

In this checkpoint you will find a path using the Breadth First Search algorithm on a map. You will plan in one of these maps, which is customized based on where you are taking the course:

<div markdown=1 style="text-align: center;">
![DC Metro Map](/assets/images/p3/dc_metro_map.jpg){:style="max-width:400px;"}
![Michigan Map](/assets/images/p3/michigan.png){:style="max-width:400px;"}
</div>

Complete the following:

- Design a way to store node data needed in BFS. Add members to the `Graph` struct to store this data.
- Complete function `getNeighbors()`. It should return the indices of the nodes connected to a given node.
- Complete function `getEdgeCosts()`. It should return the costs of the edges connected to a given node, parallel to the neighbors returned by `getNeighbors()`.
- Complete function `initGraph()`. It should create space to store data for each node in the graph and initialize any data you might need.
- Complete function `getParent()`. It should return the index of the parent node. If the node has no parent, it should return -1.
- Complete function `bfs(start, goal, g)`. It should perform Breadth First Search to find a path from node index `start` to `goal` within graph `g`.

### Code Overview

All of the code for this activity is in ```src/1_planning_in_michigan/```. The purpose of this codebase is to represent a graph as a struct in code and then implement basic graph search algorithms over that graph. The definition of the ```Graph``` is given in ```planning.h``` along with a few definitions and several declarations for functions to manipulate the graph. The functions that are declared in ```planning.h``` are implemented in ```planning.cpp```. You will work in ```planning.h``` and ```planning.cpp``` according to the items above, which are marked as tasks.

The graph you will plan over is loaded from the file ```data/planning_in_michigan/mi_graph.txt```. This graph stores the node names and connectivity of the graph pictured above.
 
## Expected Behavior

The expected behavior of the code is described in the header file ```planning.h```. By taking a read through all of the comments you should be able to get a sense of how the code fits together.

## Advanced Extensions

As an advanced extension, you may implement Depth First Search over the same graph. It is not required and is not part of your grade.

- Complete function `dfs(start, goal, g)` in ```src/1_planning_in_michigan/planning.cpp``` according to the header file ```src/1_planning_in_michigan/planning.h```. It should perform Depth First Search, using a stack instead of a queue, to find a path from node index `start` to `goal` within graph `g`.

### Testing the Extension

The test cases for this extension exist in ```test_public.cpp``` but are disabled by default (their test suite names start with ```DISABLED_```) so they don't affect your grade on the base checkpoint. Run them with ```./test_public --gtest_also_run_disabled_tests``` in the ```/build``` directory, or remove the ```DISABLED_``` prefix from ```PlanningInMichigan.DISABLED_Dfs``` to run it on its own.

## Testing

Some of the functions can be tested by running ```ctest --output-on-failure``` in the ```/build``` directory.

To run breadth first search manually, you can run the executable ```./plan_in_michigan``` in the ```/build``` directory. This runs the ```main()``` function in ```src/1_planning_in_michigan/main.cpp``` which is designed to help you see the output of your algorithm.
