# Lab 10: RL for Tic-Tac-Toe

For this lab I implemented a Q-Learning agent by following [this](https://huggingface.co/learn/deep-rl-course/unit2/q-learning) explanation.

For the state representation I used the representation from the lecture, where a state is represented by the two sets (X plays and O plays) and the goal is to achieve a sum of 15 using the [magic square](https://en.wikipedia.org/wiki/Magic_square).

My reward function is calculated as follows:

| Action                                 | Reward |
| -------------------------------------- | ------ |
| Invalid move                           | -10    |
| Could have blocked opponent but didn't | -5     |
| Blocked opponent                       | 5      |
| Won                                    | 10     |
| Lost                                   | -10    |
| Otherwise                              | 0      |
