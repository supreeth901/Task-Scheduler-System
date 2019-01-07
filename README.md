CFS Implementation

For implementing the completely fair scheduler we made some adjustments to the algorithm but did
not make any changes that would affect the core of the algorithm. We implemented the algorithm in the
following way:
1. Read the input file and sort it according to arrival time into an array
2. The first process (whenever tree is empty) is executed for quantum slice. While this process executes,
other processes might arrive and wait
3. After execution is completed, if the process still has time left, it is inserted into the tree
4. Now all the processes which have arrived while 1st process was executing are also inserted into the
tree
5. The unfairness score is calculated for each process based upon the arrival time and spent time as
unfairnessScore = arrivalTime + spentTime
6. This ensures that the process with the least spent time goes to the left most leaf
7. Now we extract the left most process and execute it by calculating the maximum_execution time as
stated above (waitingTime / no. of processes)
8. Thus, every time the process which has waited the most (or spent least time using the CPU) is selected

Data Structures and Programming Languages
As stated in the project description, we have used following two types of data structures:
1. Red Black Tree
2. Min Heap (Using priority queue)

We have implemented the CFS algorithm using the two data structures in java. We have then created a
wrapper in python to call that algorithm. All the test cases have been designed and run using the python
wrapper. We have used python since it was easier to plot graphs and generate random inputs for testing
purposes using python. User inputs are also accepted through the python UI.
