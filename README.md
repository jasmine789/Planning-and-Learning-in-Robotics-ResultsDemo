# Planning-and-Learning-in-Robotics

PR1: Making an agent get treasure with lowest cost in a Door & Key Environment by defining the problem as a deterministic shortest path problem (DSP) and using Label Correcting (LC) algorithm .

PR2: Implementing search-based planning algorithm(RTAA*) in 3D Euclidean space to make an agent elude obstacles and reach a final goal and Comparing RTAA* with RTT* algorithm(using existing library)

PR3: Balancing an inverted pendulum using Value Iteration(VI) and Policy Iteration(PI)

PR4(Group Project): Implementing SARSA, Q-learning and Deep Q-learning in Cart-pole and Lunar-lander environment

## PR1: Autonomous navigation in Door&Key Environment

This project implements autonomous navigation in a Door & Key environment to make an agent get treasure with lowest cost using Dynamic Programming algorithm with a known map. There is a key, a door and walls in the map. The agent needs to get the treasure with the lowest cost. The agent has three regular actions - move forward(MF), turn left(TL) and turn right (TR), and two special actions, pick up key(PK) and unlock door(UD).  In this project, I firstly define the problem as a deterministic shortest path problem (DSP) and then use Label Correcting (LC) algorithm to solve the problem.

The Results are demonstrated below:

|     Environment      |                         Results                          |
| :------------------: | :------------------------------------------------------: |
|  Doorkey-5x5-normal  |   ![5x5_normal](./results_demo/PR1_gif/5x5_normal.gif)   |
|  Doorkey-6x6-normal  |   ![6x6_normal](./results_demo/PR1_gif/6x6_normal.gif)   |
|  Doorkey-6x6-direct  |   ![6x6_direct](./results_demo/PR1_gif/6x6_direct.gif)   |
| Doorkey-6x6-shortcut | ![6x6_shortcut](./results_demo/PR1_gif/6x6_shortcut.gif) |
|  Doorkey-8x8-normal  |   ![8x8_normal](./results_demo/PR1_gif/8x8_normal.gif)   |
|  Doorkey-8x8-direct  |   ![8x8_direct](./results_demo/PR1_gif/8x8_direct.gif)   |
| Doorkey-8x8-shortcut | ![8x8_shortcut](./results_demo/PR1_gif/8x8_shortcut.gif) |
| Doorkey-8x8-example  |      ![example](./results_demo/PR1_gif/example.gif)      |

More analysis for each states please refer to folder:

```
./results_demo/PR1_results_analysis
```



## PR2: Implementing search-based planning algorithms in 3D Euclidean space, comparing the performance with sampling-based planning algorithms

This project implements search-based and sampling-based planning algorithms in 3D Euclidean space to make an agent elude collision and reach a final goal. RTAA* and RRT* algorithm are chosen to solve this problem and finally the project compares their performance. The RTAA* is implemented by myself and RRT* algorithm is modified based on  **https://github.com/motion-planning/rrt-algorithms**. In this project, I also wrote my own collision checking algorithm to check collision. 

The results in different maps are demonstrated below:

| MAP         | RTAA* results                                                | RRT* results                                                 |
| ----------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| flappy_bird | ![RTAA_flappy_bird](./results_demo/PR2_results/RTAA_flappy_bird.png) | ![RRT_flappy_bird](./results_demo/PR2_results/RRT_flappy_bird.png) |
| maze        | ![RTAA_maze](./results_demo/PR2_results/RTAA_maze.png)       | ![RRT_maze](./results_demo/PR2_results/RRT_maze.png)         |
| monza       | ![RTAA_monza](./results_demo/PR2_results/RTAA_monza.png)     | ![RRT_monza](./results_demo/PR2_results/RRT_monza.png)       |
| Room        | ![RRT_room](./results_demo/PR2_results/RTAA_room.png)        | ![RRT_room](./results_demo/PR2_results/RRT_room.png)         |
| single cube | ![RTAA_single_cube](./results_demo/PR2_results/RTAA_single_cube.png) | ![RTAA_single_cube](./results_demo/PR2_results/RRT_single_cube.png) |
| Tower       | ![RTAA_tower](./results_demo/PR2_results/RTAA_tower.png)     | ![RTAA_tower](./results_demo/PR2_results/RRT_tower.png)      |
| Window      | ![RTAA_window](./results_demo/PR2_results/RTAA_window.png)   | ![RRT_window](./results_demo/PR2_results/RRT_window.png)     |

A 3D rotational verion please refer to 

```
./results_demo/PR2_rotate
```



## PR3: Balancing an inverted pendulum using Value Iteration(VI) and Policy Iteration(PI)

This project implements inverting pendulum using Policy Iteration and Value Iteration. The inverting pendulum problem is formulated as an inifinite-horizon discounted stochastic optimal control problem. Then I compare between PI and VI algorithms by using some visualization. Finally, I play with different paramters to see their impact on performance.

Some results with different parameters are demonstrated below:

| Parameters                        |                          PI Results                          |                          VI results                          |
| --------------------------------- | :----------------------------------------------------------: | :----------------------------------------------------------: |
| My Baseline                       |    ![baseline_PI](./results_demo/PR3_gif/baseline_PI.gif)    |    ![baseline_VI](./results_demo/PR3_gif/baseline_VI.gif)    |
| Best Case                         |        ![best_PI](./results_demo/PR3_gif/best_PI.gif)        |        ![best_VI](./results_demo/PR3_gif/best_VI.gif)        |
| Different Starting position       | Starts with pi/2: ![PI_start_pi:2](./results_demo/PR3_gif/PI_start_pi:2.gif) | Starts with -pi/2:![VI_start_-pi:2](./results_demo/PR3_gif/VI_start_-pi:2.gif) |
| Different Starting position       | Starts with 3pi/4:![PI_start_3pi:4](./results_demo/PR3_gif/PI_start_3pi:4.gif) | Starts with -4pi/5:![VI_start_-4pi:5](./results_demo/PR3_gif/VI_start_-4pi:5.gif) |
| Large noise leads to failure case | ![exp3_fail_to_balance_sigma_5_PI](./results_demo/PR3_gif/exp3_fail_to_balance_sigma_5_PI.gif) | ![exp3_fail_to_balance_sigma_5_VI](./results_demo/PR3_gif/exp3_fail_to_balance_sigma_5_VI.gif) |



## PR4: Reinforcement Learning - implement SARSA, Q-learning and Deep Q-learning

My partner and I implement this project together.  In this project, we implement SARSA, Q-learning and Deep Q-learning to avoid a cart-pole failing down. Also, we implement these three algorithms to guide a lunar lander landing on a desired position. Finally, we compare and evaluation these three algorithms on these different environments.

The results are demonstrated below:

| Algorithm       | CartPole                                             | LunarLander                                              |
| --------------- | ---------------------------------------------------- | -------------------------------------------------------- |
| SARSA           | ![pole-sarsa](./results_demo/PR4_gif/pole-sarsa.gif) | ![lander-sarsa](./results_demo/PR4_gif/lander-sarsa.gif) |
| Q-Learning      | ![pole-ql](./results_demo/PR4_gif/pole-ql.gif)       | ![lander-ql](./results_demo/PR4_gif/lander-ql.gif)       |
| Deep Q-Learning | ![pole-dqn](./results_demo/PR4_gif/pole-dqn.gif)     | ![lander-dqn](./results_demo/PR4_gif/lander-dqn.gif)     |

