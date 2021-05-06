## Question Update
Last update: 6 May 2021

### Basic Simulation with large N
1. I did not explain clearly on how `Basic Simulation` method should handle test sets with large N in my question thus I added extra explanations here.
2. If you choose to implement **Depth First Search (DFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **return current best tour it found**.
3. If you choose to implement **Breath First Search (BFS)**, then when the searching process is taking too long to complete (longer than the maximum time you set) then it should stop the searching process and **randomly complete the remaning tour and return the tour**.
4. You can implement your own method on how to stop the searching as well, as long as it must return a valid tour when time exceeded. Valid tour simply means all nodes must be visited.
5. Please explain why you implement such methods as well.

### Sample Output with Elapsed Time
1. In the original question's sample output I did not show anything about time elapsed because it is quite hard to put that info in a pdf file.
2. I record the sample output of the program and save it as gif below.
3. The maximum execution time I set for every type of search is 1 minute.
4. Do note that I fastforwarded the gif due to Github file size limitation thus the time calculation seem not like a real time one. In your case your execution time calculation should be same with real world time.
5. You might want to study `Java.lang.System.nanoTime()` or [`Instant`](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html) with [`Duration`](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html) for elapsed time calculation purpose.
6. You might also want to study [`Carriage Return`](https://www.codespeedy.com/how-does-a-carriage-return-r-works-in-java/) in Java for progress bar printing purpose.  

![Sample Console Output](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/update/Delivery%20Tour%20Search.gif)
