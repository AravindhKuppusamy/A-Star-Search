# A* Search algorithm for solving mazes using rolling die

### Members:

1. Aravindh Kuppusamy (axk8776@rit.edu)
2. Deepak Sharma (ds5930@rit.edu)
3. Karan Jariwala (kkj1811@rit.edu)

------

### Problem Statement:

Implement an A* search algorithm in python for solving rolling-die mazes. The objective is to "roll" a die along its edges through a grid until a goal location is reached. The initial state of the search is given by the die location and orientation. Rolling die mazes contain obstacles, as well as restrictions on which numbers may face “up”.

**Constraints:**

1. The die begins with 1 on top, 2 facing up/north, and 3 facing right/east.
2. All opposite die faces add to 7 (e.g./ 2 on top + 5 on bottom = 7).
3. The number 6 should never be face up on the die.
4. The number 1 must be on top of the die when the goal location is reached.

------

### Approach:

**Graph search** is a perfect fit for this project, allowing paths to previously visited nodes to be pruned, and equally importantly, ensuring that the program will terminate when we have exhausted the state space when a solution does not exist, rather than repeatedly visiting previous states, producing an infinite loop. 

**A\* Search** goes one step ahead in the graph search with the use of heuristics which makes the algorithm to find the path faster. We have implemented different heuristics that are admissible and consistent for use with our A* search function. The heuristics we implemented are **Manhattan Distance**, **Diagonal Distance**, **Euclidean Distance**, and **Fancy Manhattan Distance** which is our customized version of Manhattan Distance.

------

### Execution of program:

**Main file name:** rdMaze.py

**Python version:** 3.5.1

**Required packages:** numpy, matplotlib

#### Options to execute program:

 ```shell
   # python3 rdMaze.py <Maze filename>
   - Will produce the output in the console for the given maze with all the heuristics ('fancy_manhattan', 'manhattan', 'euclidean', 'diagonal').
   ```

 ```shell
   # python3 rdMaze.py <Maze filename> <Heuristic name>
   - Will produce the output in the console for the given maze and heuristic.
   ```

 ```shell
   # python3 rdMaze.py
   - Will be prompted to enter the maze filename and also the heuristics you want to use in A* search. Will produce the output in the console for the given maze and heuristic.
   ```

   
   where,

   | Parameters          | E.g:        |
   | ------------------- | ----------- |
   | <Maze filename>   | "map2.txt"  |
   | \<Heuristic name\> | "manhattan" |



### Output:

Below is the the output when we run A* search on map-2 with Euclidean distance as heuristics.

```shell
python rdMaze.py map2.txt euclidean
```

```shell
|------------- STARTING MAZE--------------|

S . . . . 
. . * * * 
. * . . G 
. . . . . 
* . . . . 

|------------- STARTING DICE ORIENTATION--------------|

	  2							 NORTH
	  |	 	 	 	 	 	 	  |
4 - 1 / 6 - 3		 LEFT - TOP / BOTTOM - RIGHT
	  |	 	 	 	 	 	 	  |
	  5							 SOUTH

|-------------------- MOVE: 0--------------------|

# . . . . 
. . * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 1--------------------|

# . . . . 
# . * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 2--------------------|

# . . . . 
# # * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 3--------------------|

# # . . . 
# # * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 4--------------------|

# # . . . 
# # * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 5--------------------|

# # . . . 
# # * * * 
. * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 6--------------------|

# # . . . 
# # * * * 
# * . . G 
. . . . . 
* . . . . 

|-------------------- MOVE: 7--------------------|

# # . . . 
# # * * * 
# * . . G 
# . . . . 
* . . . . 

|-------------------- MOVE: 8--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . . 
* . . . . 

|-------------------- MOVE: 9--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . . 
* # . . . 

|-------------------- MOVE: 10--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . . 
* # # . . 

|-------------------- MOVE: 11--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . . 
* # # # . 

|-------------------- MOVE: 12--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . . 
* # # # # 

|-------------------- MOVE: 13--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . . # 
* # # # # 

|-------------------- MOVE: 14--------------------|

# # . . . 
# # * * * 
# * . . G 
# # . # # 
* # # # # 

|-------------------- MOVE: 15--------------------|

# # . . . 
# # * * * 
# * . # G 
# # . # # 
* # # # # 

|-------------------- MOVE: 16--------------------|

# # . . . 
# # * * * 
# * . # # 
# # . # # 
* # # # # 

|------------- DICE--------------|

	  5							 NORTH
	  |	 	 	 	 	 	 	  |
3 - 1 / 6 - 4		 LEFT - TOP / BOTTOM - RIGHT
	  |	 	 	 	 	 	 	  |
	  2							 SOUTH

|---------------- PERFORMANCE METRICS -----------------|

No. of moves in the solution                    :  16
No. of nodes put on the queue                   :  51
No. of nodes visited / removed from the queue   :  42

|------------------------------------------------------|

```

### Performance:

Following graph shows the number of nodes generated and visited for all the maps with different heuristics.

![](https://github.com/AravindhKuppusamy/A-Star-Search/blob/master/output/performance.png)

------

### Report:

To read more about this project, please refer to the project [report](https://github.com/AravindhKuppusamy/A-Star-Search/blob/master/Project_Report.pdf).
