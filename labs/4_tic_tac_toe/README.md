# Lab 10: RL for Tic-Tac-Toe

For this lab, I worked alone but exchanged some ideas with [Matteo](https://github.com/Matteo-Pietro-Pillitteri/Computational-Intelligence.git) and used the Montecarlo code from the lecture. I also read [this](https://ai.stackexchange.com/a/10033) answer from stackexchange regarding using q-learning for a scenario with two players.

I implemented a Q-Learning agent by following [this](https://huggingface.co/learn/deep-rl-course/unit2/q-learning) explanation.

For the state representation I used the representation from the lecture, where a state is represented by the two sets (X plays and O plays) and the goal is to achieve a sum of 15 using the [magic square](https://en.wikipedia.org/wiki/Magic_square).

For simplicity, I assumed the agent always plays first.

My reward function is calculated as follows:

| Action                                 | Reward |
| -------------------------------------- | ------ |
| Could have blocked opponent but didn't | -5     |
| Blocked opponent                       | -5     |
| Won                                    | +10    |
| Lost                                   | -10    |
| Otherwise                              | +0     |

For the q-learning algorithm implementation:

- I run the training loop for $500.000$ episodes with $\alpha = 0.1$ and $\gamma = 0.99$.
- I update the q-table using the formula $Q(S_t, A_t) \leftarrow Q(S_t, A_t) + \alpha(R_{t+1} + \gamma max_a Q(S_{t+2}, a) - Q(S_t, A_t))$.
  - I use $S_{t+2}$ instead of $S_{t+1}$ because $S_{t+1}$ is the opponent's turn.
- I train against an agent that plays randombly.

I also added an adaptation of q learning which uses $S_{t+1}$, as it interprets choosing the best next action as choosing the symetric of the worst action as O. I am still unsure on whether or not this is correct, but I left it here as it was part of my reasoning and it seems to get slightly better results.

To test my agent, I played $5.000$ games.

When running the results yourself (or in my published notebook) the results can be different due to the inherent randomness of my implementation and the randomness of the opponent during training/testing. That said, during my test run, my results were:

```
Q-LEARNING AGAINST RANDOM Wins: 4172, Draws: 355, Losses: 473
Winning Percentage: 83.44%
Draw Percentage: 7.10%
Loss Percentage: 9.46%


MY Q-LEARNING AGAINST RANDOM Wins: 4253, Draws: 344, Losses: 403
Winning Percentage: 85.06%
Draw Percentage: 6.88%
Loss Percentage: 8.06%


MONTECARLO AGAINST RANDOM Wins: 2508, Draws: 998, Losses: 1494
Winning Percentage: 50.16%
Draw Percentage: 19.96%
Loss Percentage: 29.88%
```
