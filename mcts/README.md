## Monte Carlo Tree Search with Nested Rollout Policy Adaptation

![NRPA](https://github.com/NeverOnTimeSdnBhd/Delivery-Instances/blob/main/mcts/NRPA.gif)

### Hyperparameter
1. We have `level`, `iterations` and `alpha`.
2. `level` is just the number of level for MCTS search tree (the one in top right inside gif above).
3. `iterations` refers to the number of nodes in every level.
4. `aplha` is just a hyperparameter to update the policy (you can imagine it like a learning rate, aka. how much you want the policy to adapt to every solution it found).
5. If you are not sure about how to edit it, then just follow the preset hyperparameter value given inside psedocode.

### Policy
1. In reinforcement learning (RL), a policy $\pi(s)$ comprises the suggested actions that the agent should take for every possible state s \in S.
2. In our problem context, agent refers to every vehicle and state refer to every station/node/customer.
3. In pseudocode, the `global policy` is the policy defined above. It is a metric/reference for us to select every next move when we perform rollout. 
4. You can imagine it like a probability distribution, let say I am at node A, I can go node B, C and D as my next node, then global policy is just the metric that tell me which next node I should go based on previous trial (Gif above shows you how policy is used when perform rollout, eg. when we want find next best next move from node 0, we check first row in the policy which comprises information about how favor node 0 select every other nodes as its next move).
5. Let say my previous trial tell me that from A to B will have much lower cost than from A to C, then my policy should convey this information (It is actually done through some calculations that I don't want go through here for the sake of simplicity).
6. In pseudocode, the `policy` is just a variable to store all levels' policies (refer to gif).
7. Imagine you have 3 levels (the one shown in diagram above), a global policy is of size N x N, where N is the number of nodes (so let say if we have 5 nodes then a global policy is of size 5x5), then the policy will be 3 x N x N (3 N x N global policies).
8. The sample in gif above is with N = 5 and level = 3, so the `policy` will be of size 3 x 5 x 5.

### Functions/Method Explanation
1. function `search` is the main function to perform MCTS with NPRA search.
2. function `adapt` is the function to update policy based on rollout result (a tour).
3. function `rollout` is the function that search for routes for the tour according to policy. This function is quite similar to other search you do (BFS/DFS or Greedy). It is just something about how I assign route to every vehicle and nothing special (the only thing special is how it select next move which is encapsulated in `select_next_move` function).
4. function `select_next_move` is the function that decide which node to go next from current node based on the policy. If you do not understand how exactly this function is doing is fine, just follow the pseudocode, all formula are given inside.

### Searching Concept
1. The whole idea of this search is instead of searching blindly, I search for best tour based on my past experiences (If you print out the result of every rollout you should find that the result tour is getting better and better in term of cost).
2. Initially from level 2, I copy level 2 policy value (initialized with all 0s first) to level 1 policy and go down one layer in the search tree, then copy level 1 policy value to level 0 policy and go down one more layer to level 0.
3. When reach level 0, I perform rollout (search for a tour) based on the level 0 policy (refer gif above: dark orange colour in the global policy refer to the row we refer when we try to search a next move for a specific node, which is highlighted in orange also in bottom right rollout tree).
4. After I searched a tour, I update my level 0 policy based on the tour found and its cost (use the `adapt` function, don't have to understand the formula, just let it go first, just follow what is inside the pseudocode, it is out of the scope here).
5. I then update the level 1 policy from level 0 policy.
6. Then I copy the level 1 policy to level 0 policy again and go down to second branch of level 0 and perform rollout again.
7. This process is repeated untill all iterations are completed (all nodes in top right search tree are explored).

### Online References
As requested, I put some online references here. However, I suggest you stay away from these resources. They are all research papers and if you really want to understand fully it will take time. My advise for you is just have an overall image on how this thing works is enough. You can revise back this search in detail when you had taken more courses in your future semesters. The purpose I give the pseudocode is to help you code even you don't understand the concept fully.

Another thing I want to emphasize is, **there is no source code or full implementation available online**. If you are trying to search for a complete solution, then you can give up and save your time instead as I had tried it for you. All you can find is pseudocodes and they are even more simple than what I gave you all here.

1. https://www.researchgate.net/publication/281589755_Monte-Carlo_Tree_Search_for_Production_and_Logistics
2. https://ieeexplore.ieee.org/stamp/stamp.jsp?tp=&arnumber=7856159
3. https://hal.inria.fr/hal-01406457/document
