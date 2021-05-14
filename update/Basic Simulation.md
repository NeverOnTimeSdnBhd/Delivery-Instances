## Basic Simulation
As per discussion in [Question regarding Basic simulation #1 (Issue)](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/issues/1), I create this documentation to avoid confusion on the meaning of BFS and DFS implementation in this problem context.

### Sample Graph
Assuming we want to find a path from A to P.
![graph](https://user-images.githubusercontent.com/80279898/118280686-06486500-b4ff-11eb-926e-f1b73d174ead.png)
_\**Image from Data Structure 2020/2021 Topic 9 Graph lecture slide_

### Conventional DFS / BFS
It is a blind search without any evaluation metric/cost. So to search from A to P, we can imagine it as a search tree as shown below.  
Note that both DFS and BFS stop searching once they searched **a path** from A to P.
![Conventional DFS / BFS](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/update/DFS-BFS.gif)

### Adapted DFS / BFS For Lowest Cost
You can implement DFS / BFS to search for the lowest cost path. The trick here is just search through whole search tree.  
Note that both DFS and BFS here did not stop searching after they found the first possible path. They store the path instead and continue searching for next possible path until whole search tree is explored.
![Adapted DFS / BFS](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/update/DFS-BFS(Adapted).gif)

### Extra Note
Of course, in this problem you have to consider vehicle and their capacities. It is not as simple as the example I shown above. This part I would like to leave it to you for you to think.

### Open Discussion
Let us consider another application of DFS / BFS: **Tic-Tac-Toe Game Search**.  
In order to find the best move to do next, we can make the current state of the game as root node of a search tree and explore all possible move from current state as shown in diagram below.

![Tic-Tac-Toe Game Tree](https://user-images.githubusercontent.com/80279898/118286234-d43a0180-b504-11eb-87c9-2e62023afd0c.png)

So, 
1. let's think about which type of search is most efficient/suitable in this application? Is it BFS? or DFS? or even adapted DFS/BFS? Why?
2. Then, which type of search is more efficient/suitable for the `Sample Graph` example? Why?
3. Last but not least, do you know the data structure you choose to represent the graph will greatly affect your searching performance too? So what is the more suitable data structure to represent your problem contexts (for both applications) and why?
4. You might want to consider the same thing for `Basic Simulation` in you assignment too.
