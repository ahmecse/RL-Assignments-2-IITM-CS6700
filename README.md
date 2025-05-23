# CS6700: Reinforcement Learning - Programming Assignment 2

## Overview
This assignment focuses on implementing and comparing variants of Dueling-DQN and Monte-Carlo REINFORCE algorithms across two Gymnasium environments: Acrobot-v1 and CartPole-v1.

## Environments
- **Acrobot-v1**: The objective is to swing the free end of a two-link chain above a certain height.
- **CartPole-v1**: The goal is to balance a pole placed upright on a moving cart.

## Algorithms
### Dueling-DQN
Two variants of Dueling-DQN are implemented and compared:
- **Type-1**: Decomposes Q-value into state value and advantage streams.
- **Type-2**: Estimates Q-values by considering the maximum advantage.

### Monte-Carlo REINFORCE
Two update methods for MC REINFORCE are compared:
- **Without Baseline**: Updates policy parameters using Monte Carlo sampling.
- **With Baseline**: Utilizes a baseline updated by the TD(0) method for policy optimization.

## Instructions
- Use a discount factor (γ) of 0.99.
- Tune hyperparameters to minimize regret.
- Average results over 5 random seeds.
- Plot episodic return vs. episodic number.

## Results
Four plots are included to compare the performance of the algorithm variants in both environments.
