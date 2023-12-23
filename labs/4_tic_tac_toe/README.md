# Lab 10: RL for Tic-Tac-Toe

For this lab I implemented a Q-Learning agent by following [this](https://huggingface.co/learn/deep-rl-course/unit2/q-learning) explanation.

For the state representation I used the representation from the lecture, where a state is represented by the two sets (X plays and O plays) and the goal is to achieve a sum of 15 using the [magic square](https://en.wikipedia.org/wiki/Magic_square).

My reward function awards -100 points each time the agent tries to play an ilegal move, -10 for each loss, 5 for each time it blocks an opponent's win and 10 for each win.

## To-Do

- [ ] Move code to classes;
- [ ] Compare Q-Learning with Montecarlo from the lecture implementation;
