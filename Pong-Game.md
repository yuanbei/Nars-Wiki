This example is one of the examples that compare the performances of NARS and Reinforcement Learning(Q-Learning) algorithm on the same problem.

The goal of this game is to let the system to learn how to automatically adjusting the position of the bar so the bar could catch the ball.

One of the major differences between NARS and Q-Learning on a theoretical level is, that NARS, differently than Q-Learning, does not assume the existence of a unique state that unambiguously identifies the relevant aspects of the current situation the agent is in [Assumptions of Decision-Making Models in AGI](http://agi-conf.org/2015/wp-content/uploads/2015/07/agi15_wang_assumptions.pdf). Instead, NARS only assumes, that there will be perceivable regularities in its experience that can be summarized and exploited, mainly by usage of its Induction and Revision rules. This, as we will see later, makes it possible to apply NARS in scenarios of higher input complexity, where states rarely repeat, and a classifier would have to be used on input-side to make Q-Learning applicable. For our comparison with RL in its domain, we can, however, assume that NARS receives the same information as the QL agent, as we will see now.

**Click the Image for the Demo video**

[![Pong Demo](https://github.com/opennars/opennars/blob/d6cb49a387f9e7fca979b2735b3d66c27a9c6912/pong.png)](https://www.youtube.com/watch?v=84nMQX444hk "Pong Game")

# Results

The learning parameters were α := 0:1 and γ := 0:8, with an exploration rate of 0:1. Additionally the simulation ran with 26 frames per second, leading to approximately 17 seconds for the ball to move from right to left and approximately 14 from top to bottom. Also in this simulation, the paddle can move twice as fast as the ball

### Right Policy acquired

| Learning Time  | Q-Learning Success Rate | NARS Success Rate  |
| -------------  | -------------------     | ------------       |
|   1 Minute     |        100/100          |       97/100       |

After an additional minute of time, both systems had a very low error rate, which further suggests that the right policy was learned by both systems

### Error Rate

| Additional Runtime  | Q-Learning Misses : Hits | NARS Misses : Hits  |
| -------------  | ------------- | ------------  |
| 3 Minute   | 1 : 12  | 2 : 12  |


What we see is that the learning parameters we chose for Q-Learning were sufficient for this task. And in comparison, the Q-Learning method is more robust in learning this task, as it learned the right policy in all 100 trials while NARS failed in 3=100 cases in our test run. The lower robustness in learning this task in a short time was expected and can be
explained by the control system of NARS which is still under testing and tuning. When both systems acquired the right policy, both worked quite reliable. Here NARS’s mistakes can be explained by its probabilistic control design, while Q-Learning error rate could in principle be reduced by letting the Exploration Rate parameter shrink over time.

Also, see how NARS get improved in most recent versions.

Pong Version 3.0.0

![pong_version_3.0.0](https://github.com/opennars/Metrics/blob/master/OpenNARS%20version%20performance%20graphs/Pong_v3_0_0.png)

Pong Version 3.0.1

![Pong Version 3.0.1](https://github.com/opennars/Metrics/blob/master/OpenNARS%20version%20performance%20graphs/Pong_v3_0_1.png)

Pong Version 3.0.2

![Pong Version 3.0.2](https://github.com/opennars/Metrics/blob/master/OpenNARS%20version%20performance%20graphs/Pong_v3_0_2.png)
