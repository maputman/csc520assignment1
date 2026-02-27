# csc520assignment1
We based our implementation on the given Harry Potter example. There are 3 pieces of evidence hidden around the map that Harry must find before he reaches a "safe" room. Only then is the search complete. We have implemented depth and breadth first searches. <br>
To compile this code, simply download the raw "harry.xml" file in the code folder. Then upload that file into SNAP. <br>
To run the project in SNAP, click the pink "Sprite" circle on the right. In the Scripts tab, there should be a small block of code starting with "when green flag clicked". Press the block of code to generate the map. Do this each time before running a new search. Then click the "Harry" sprite on the right. If you scroll to the bottom of the Scripts tab, there should be another small block of code that begins with "when green flag clicked." You can input the name of any room from the map you want to begin your search in into the first text input. You can also input the type of search you want to run (BFS or DFS) into the second text input. <br>
We have represented the state space graph using an adjacency list stored in the WorldMap list variable. Each room stores a room name (unique identifier), neighbors (list of [neighbor name, edge cost] pairs), h(n) (heuristic value in case we want to implement A* in the future), type (room type: standard, goal, or evidence), and x, y coordinates for visualization. <br>
States are represented as lists containing [room name, evidence collected, path cost, depth]. The room name is the current location. The evidence collected is a global variable, but the state version keeps track of if there is evidence within a specific room. The path cost is the accumlated cost from the start. The depth is the number of actions taken (aka path length) to add to our project report. <br>
Actions are implicit in our implementation. They are simply moving from one room to neighboring room via an edge. Transition function is implemented in the expand node block. We got the current room from the state, look up neighbors using the neighborsOf block, create a new state for each unexplored neighbor, and add new states to the fringe. <br>
The goal test is implemented in the isGoal? block. It checks that the global evidence collected list contains all 3 pieces of evidence. It checks if the current room is a goal room and returns ture only if both these conditions are met. <br>

*Loading Test Cases* <br>
BFS: <br>
Test 1: <br>
In the "Harry" sprite, scroll to the bottom of the Scripts tab. There is a small block of code that begins with "when green flag clicked." Input "Great Hall" into the first text input and input "BFS" into the second text input. <br>

Test 2: <br>
In the "Harry" sprite, scroll to the bottom of the Scripts tab. There is a small block of code that begins with "when green flag clicked." Input "Dungeons" into the first text input and input "BFS" into the second text input. <br>

Test 3: <br>
In the "Harry" sprite, scroll to the bottom of the Scripts tab. There is a small block of code that begins with "when green flag clicked." Input "Cursed Objects Vault" into the first text input and input "BFS" into the second text input. <br>


DFS: <br>

The project produces path length (announced when goal is found) and expanded node count (can be viewed by clicking the "expanded count" variable in the Variables section of the project). The nodes visited are marked by Harry clones and the room names are announced as each one is visited.


*Assumptions*
* All rooms will always be reachable from any starting state
* Harry has perfect information. He knows the whole map and room connections upfront.
* Evidence can be collected in any order
* Only one Harry is searching at a time

*Limitations*
* A state can be added to the fringe multiple times with different costs before it is officially explored
* Evidence is tracked globally, not in states. This simplified our implementation.
* Visualization is limited by SNAP!. We aren't able to visualize multiple paths simultaneously

To see the rest of the details on our test cases and program, look at the project report in the docs folder.
