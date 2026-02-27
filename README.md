# csc520assignment1
We based our implementation on the given Harry Potter example. There are 3 pieces of evidence hidden around the map that Harry must find before he reaches a "safe" room. Only then is the search complete.
To compile this code, simply download the raw "harry.xml" file in the code folder. Then upload that file into SNAP. <br>
To run the project in SNAP, click the pink "Sprite" circle on the right. In the Scripts tab, there should be a small block of code starting with "when green flag clicked". Press the block of code to generate the map. Do this each time before running a new search. Then click the "Harry" sprite on the right. If you scroll to the bottom of the Scripts tab, there should be another small block of code that begins with "when green flag clicked." You can input the name of any room from the map you want to begin your search in into the first text input. You can also input the type of search you want to run (BFS or DFS) into the second text input. <br>



How have you designed your infrastructure (code that represents the graph, actions,
transition function, etc)

*Loading Test Cases* <br>
BFS: <br>
Test 1: <br>
DFS: <br>


what outputs the project produces (path, cost, expansions, trace)


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
