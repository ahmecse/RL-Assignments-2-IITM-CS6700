# CS6700 Programming Assignment 2: Reinforcement Learning

[![Python](https://img.shields.io/badge/python-3.8+-blue.svg)](#prerequisites)

A comparative study of Dueling-DQN and Monte Carlo REINFORCE algorithms on the *Acrobot-v1* and *CartPole-v1* environments using OpenAI Gymnasium.

---

## 📋 Table of Contents

1. [Overview](#overview)
2. [Environments](#environments)
3. [Algorithms](#algorithms)

   * [Dueling DQN Variants](#dueling-dqn-variants)
   * [Monte Carlo REINFORCE Variants](#monte-carlo-reinforce-variants)
5. [Usage](#usage)
6. [Results](#results)
7. [Project Structure](#project-structure)


---

## 📝 Overview

This repository contains implementations of two model-free RL algorithms:

* **Dueling-DQN**: Enhances DQN by decomposing the Q-function into state-value and advantage streams.
* **Monte Carlo REINFORCE**: A policy-gradient method using full-episode returns, with and without baseline.

Agents are trained on:

* **Acrobot-v1**: Swing-up control of a two-link pendulum chain.
* **CartPole-v1**: Balancing a pole on a cart via discrete force actions.

We compare each algorithm’s two variants over 5 random seeds, plotting mean ± variance of episodic returns.

---

## 🎮 Environments

| Environment     | Description                                                                  | Gymnasium Link                                                                                                                                 |
| --------------- | ---------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| **Acrobot-v1**  | Apply torques to swing a two-link pendulum to a target height.               | [https://gymnasium.farama.org/environments/classic\_control/acrobot/](https://gymnasium.farama.org/environments/classic_control/acrobot/)      |
| **CartPole-v1** | Balance an inverted pendulum on a moving cart by applying left/right forces. | [https://gymnasium.farama.org/environments/classic\_control/cart\_pole/](https://gymnasium.farama.org/environments/classic_control/cart_pole/) |

---

## ⚙️ Algorithms

### Dueling DQN Variants

![Dueling-DQN Architecture](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Dueling-DQN.JPG)

### Monte Carlo REINFORCE Variants

![MC-REINFORCE Update](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Monte-Carlo%20REINFORCE.JPG) 
---

## ▶️ Usage

### Training

Run the training scripts for each algorithm:

```bash
# Dueling-DQN (Type-1 vs Type-2) on Acrobot
python train_dueling_dqn.py --env Acrobot-v1 --variant type1
python train_dueling_dqn.py --env Acrobot-v1 --variant type2

# REINFORCE (with/without baseline) on CartPole
python train_reinforce.py --env CartPole-v1 --baseline False
python train_reinforce.py --env CartPole-v1 --baseline True
```

All scripts accept these flags:

| Flag         | Description                                 | Default     |
| ------------ | ------------------------------------------- | ----------- |
| `--env`      | Gym environment name                        | CartPole-v1 |
| `--variant`  | `type1` or `type2` for dueling DQN          | type1       |
| `--baseline` | `True` or `False` for MC-REINFORCE baseline | False       |
| `--seed`     | Random seed (runs averaged over 5 seeds)    | 0           |
| `--episodes` | Number of training episodes                 | 500         |

---

## 📊 Results

Plots are saved in the `results/` directory. Below are the performance comparisons (mean ± variance over 5 seeds):

|                                                       **Acrobot Dueling-DQN**                                                       |                                                        **CartPole Dueling-DQN**                                                       |
| :---------------------------------------------------------------------------------------------------------------------------------: | :-----------------------------------------------------------------------------------------------------------------------------------: |
| ![Acrobot Dueling-DQN](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Dueling-DQN_Acrobot-v1_Plot.png) | ![CartPole Dueling-DQN](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Dueling-DQN_CartPole_v1_Plot.png) |


|                                                               **Acrobot REINFORCE**                                                               |                                                              **CartPole REINFORCE**                                                             |
| :-----------------------------------------------------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------------------------------------------------: |
| ![Acrobot REINFORCE](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Monte_Carlo_REINFORCE_WithOut_BeseLine_Plot.png) | ![CartPole REINFORCE](https://raw.githubusercontent.com/ahmecse/RL-Assignments-2-IITM-CS6700/main/Monte_Carlo_REINFORCE_With_BeseLine_Plot.png) |

---

## 🗂️ Project Structure

```
.
├── train_dueling_dqn.py   # Training script for Dueling-DQN
├── train_reinforce.py     # Training script for MC-REINFORCE
├── results/               # Generated plots
├── README.md              # Project overview
└── requirements.txt       # Python dependencies
```

---
