## Monte Carlo Tree Search with Nested Rollout Policy Adaptation

![image](https://user-images.githubusercontent.com/80279898/117935314-2bd64280-b336-11eb-8325-56b61f407930.png)

1. function search is the main function to search.
2. function adapt is the function to update policy based on rollout result (a tour).
3. function rollout is the function that search for routes for the tour according to policy.
4. function select_next_move is the function that decide which node to go next from current node based on the policy.
5. Global policy is a metric/reference for us to select every next move when we perform rollout. 
6. You can imagine it like a probability distribution, let say I am at node A, I can go node B, C and D as my next node, then global policy is just the metric that tell me which next node I should go based on previous trial.
7. Let say my previous trial tell me that from A to B will have much lower cost than from A to C, then my policy should convey this information (It is actually done through some calculations that I don't want go through here for simplicity sake).
8. Policy is just a variable to store all levels' policies.
9. Imagine you have 3 levels (the one shown in diagram above), a global policy is of size N x N, where N is the number of nodes (so let say if we have 5 nodes then a global policy is of size 5x5), then the policy will be 3 x N x N (3 N x N global policies).
10. The whole idea of this search is instead of searching blindly, I search for best tour based on my past experiences (If you print out the result of every rollout you should find that the result tour is getting better and better in term of cost).
11. Initially from level 2, I copy level 1 policy and go down one layer in the search tree, then copy level 0 policy and go down one more layer to level 0.
12. When reach level 0, I perform rollout (search for a tour) based on the level 0 policy.
13. After I searched a tour, I update my level 0 policy based on the tour found and its cost.
14. I then copy the level 0 policy to level 1 policy.
15. Then I copy the level 1 policy to level 0 policy and go down to second branch of level 0 and perform rollout again.
16. This process is repeated untill all iterations (iteration is a hyperparameter you fixed).
