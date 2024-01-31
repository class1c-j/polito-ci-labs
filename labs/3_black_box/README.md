# Lab 9

## Algorithm

- I implemented a $(\lambda, \mu)$ strategy enhanced with islands and elitism concepts;
- For mutation I randomly flip a percentage of bits in the genome in the range of 1% and 5%;
- For crossover I do two point crossover;
- I stop the algorithm after 250 consecutive generations with no improvement for instances 1 and 2 and 500 for instances 5 and 10;

## Results

Here I present the results I got in my test run. You may see different results on the commited notebook or running locally due to the random nature of the algorithm.

### Single population (more efficient)

- For **problem instance 1** i got fitness 0.73, 275374 fitness calls;
- For **problem instance 2** i got fitness 0.612, 251329 fitness calls;
- For **problem instance 5** i got fitness 0.296, 840962 fitness calls;
- For **problem instance 10** i got fitness 0.171, 841209 fitness calls;

### 10 islands (better fitness, but more expensive)

- For **problem instance 1** i got fitness 0.835, 2246549 fitness calls;
- For **problem instance 2** i got fitness 0.722, 2510219 fitness calls;
- For **problem instance 5** i got fitness 0.406, 5178027 fitness calls;
- For **problem instance 10** i got fitness 0.2956, 5808903 fitness calls;

- This code was updated after the deadline because I found a small typo. The in-time commit is [b96bac0db55ae0592bc3b18ed6e7924225a7dba7](https://github.com/class1c-j/polito-ci-labs/tree/b96bac0db55ae0592bc3b18ed6e7924225a7dba7/labs/3_min_calls)
