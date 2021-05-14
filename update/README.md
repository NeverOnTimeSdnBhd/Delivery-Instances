## Question Update
Last update: 6 May 2021

### Basic Simulation Explanation/Clarification
Please refer [`Basic Simulation.md`](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/update/Basic%20Simulation.md) for more information.

### Basic Simulation with large N
1. I did not explain clearly on how `Basic Simulation` method should handle test sets with large N in my question thus I added extra explanations here.
2. If you choose to implement **Depth First Search (DFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **return current best tour it found**.
3. If you choose to implement **Breath First Search (BFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **randomly complete the remaning tour and return the tour**.
4. You can implement your own method on how to stop the searching as well, as long as it must return a valid tour when time exceeded. Valid tour simply means all nodes must be visited.
5. Please explain why you implement such methods as well.

### Sample Output with Elapsed Time
1. In the original question's sample output I did not show anything about time elapsed because it is quite hard to put that info in a pdf file.
2. I record the sample output of the program for one of the test case and save it as gif below. I also copy paste the output below the gif.
3. The maximum execution time I set for every type of search is 1 minute.
4. Do note that I fastforwarded the gif due to Github file size limitation thus the time calculation seem not like a real time one. In your case your execution time calculation should be same with real world time.
5. You might want to study `Java.lang.System.nanoTime()` or [`Instant`](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html) with [`Duration`](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html) for elapsed time calculation purpose.
6. You might also want to study [`Carriage Return`](https://www.codespeedy.com/how-does-a-carriage-return-r-works-in-java/) in Java for progress bar printing purpose.
7. Please note that elapsed time and search result might be different depending on your devices.

![Sample Console Output](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/update/Delivery%20Tour%20Search.gif)
```
Basic Simulation
Time elapsed: |============================================================| 60s (Searching is forced to stop!)
Tour
Tour Cost: 2254.855192759892
Vehicle 1
0 -> 3 -> 1 -> 10 -> 6 -> 0
Capacity: 24
Cost: 528.198890047597
Vehicle 2
0 -> 8 -> 9 -> 4 -> 0
Capacity: 23
Cost: 272.3023299146489
Vehicle 3
0 -> 5 -> 7 -> 0
Capacity: 22
Cost: 389.09950131136236
Vehicle 4
0 -> 2 -> 11 -> 0
Capacity: 21
Cost: 300.6806031394681
Vehicle 5
0 -> 12 -> 0
Capacity: 8
Cost: 186.09674903125006
Vehicle 6
0 -> 13 -> 0
Capacity: 21
Cost: 154.1557653803452
Vehicle 7
0 -> 14 -> 15 -> 0
Capacity: 16
Cost: 336.23049175303936
Vehicle 8
0 -> 16 -> 0
Capacity: 20
Cost: 88.0908621821809

Greedy Simulation
Time elapsed: |                                                            | 0s
Tour
Tour Cost: 2855.6680271242603
Vehicle 1
0 -> 8 -> 14 -> 9 -> 11 -> 7 -> 6 -> 0
Capacity: 24
Cost: 508.499802988973
Vehicle 2
0 -> 16 -> 10 -> 0
Capacity: 23
Cost: 358.3531829695121
Vehicle 3
0 -> 13 -> 0
Capacity: 21
Cost: 154.1557653803452
Vehicle 4
0 -> 12 -> 3 -> 15 -> 0
Capacity: 22
Cost: 470.82334189148287
Vehicle 5
0 -> 4 -> 0
Capacity: 12
Cost: 272.1837614553815
Vehicle 6
0 -> 2 -> 0
Capacity: 18
Cost: 279.1773629791642
Vehicle 7
0 -> 5 -> 0
Capacity: 21
Cost: 387.55128692858216
Vehicle 8
0 -> 1 -> 0
Capacity: 14
Cost: 424.92352253081935

MCTS Simulation
Time elapsed: |============================================================| 60s (Searching is forced to stop!)
Tour
Tour Cost: 2187.291352798425
Vehicle 1
0 -> 10 -> 6 -> 1 -> 9 -> 3 -> 0
Capacity: 24
Cost: 658.6862440359656
Vehicle 2
0 -> 5 -> 7 -> 0
Capacity: 22
Cost: 389.09950131136236
Vehicle 3
0 -> 11 -> 15 -> 4 -> 0
Capacity: 22
Cost: 337.95372239117205
Vehicle 4
0 -> 16 -> 0
Capacity: 20
Cost: 88.0908621821809
Vehicle 5
0 -> 2 -> 0
Capacity: 18
Cost: 279.1773629791642
Vehicle 6
0 -> 14 -> 12 -> 0
Capacity: 17
Cost: 264.0033790216378
Vehicle 7
0 -> 8 -> 0
Capacity: 11
Cost: 16.12451549659727
Vehicle 8
0 -> 13 -> 0
Capacity: 21
Cost: 154.15576538034497
```
