## Question Update
Last update: 6 May 2021

### Basic Simulation with large N
1. I did not explain clearly on how `Basic Simulation` method should handle test sets with large N in my question thus I added extra explanations here.
2. If you choose to implement **Depth First Search (DFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **return current best tour it found**.
3. If you choose to implement **Breath First Search (BFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **randomly complete the remaning tour and return the tour**.
4. You can implement your own method on how to stop the searching as well, as long as it must return a valid tour when time exceeded. Valid tour simply means all nodes must be visited.
5. Please explain why you implement such methods as well.
