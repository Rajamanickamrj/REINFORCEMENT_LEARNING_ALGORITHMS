# CartPole Reinforcement Learning

## Introduction
CartPole is a classic reinforcement learning (RL) problem where an agent must balance a pole on a moving cart by applying forces left or right.
It is widely used as a benchmark for RL algorithms and is available in OpenAI Gym as `CartPole-v1`.

## Problem Setup
- **Cart**: Moves left or right on a track.
- **Pole**: Hinged on the cart, free to fall.
- **Objective**: Prevent the pole from falling over by applying forces to the cart.

## Environment Details

| Parameter        | Description                                    |
|------------------|------------------------------------------------|
| **State Space**  | 4 continuous variables:                        |
|                  | 1. Cart position \(x\)                         |
|                  | 2. Cart velocity \(\dot{x}\)                   |
|                  | 3. Pole angle \(\theta\)                       |
|                  | 4. Pole angular velocity \(\dot{\theta}\)      |
| **Action Space** | 2 discrete actions:                            |
|                  | 1. Move cart left                              |
|                  | 2. Move cart right                             |
| **Rewards**      | +1 for every timestep the pole remains upright |
| **Termination**  | Episode ends if:                               |
|                  | 1. Pole angle > 12° (too tilted)               |
|                  | 2. Cart moves too far (\(x > 2.4\))            |                
|                  | 3. Max episode length reached (500 steps)      |

## Why is CartPole Important?
- **Simple but effective**: Demonstrates RL concepts with minimal complexity.
- **Benchmark for RL**: Used for evaluating algorithms like Q-learning, Deep Q-Networks (DQN), and Policy Gradient methods.
- **Real-world analogy**: Similar to controlling rockets, robotic arms, or autonomous balancing systems.

## Topics Covered

### 1. CartPole Balancing with Random Policy
- The agent selects actions randomly without considering the environment’s state.
- Usually leads to poor performance as no learning is involved.
- Often used as a baseline to compare with learning-based policies.

### 2. Unified Notation for Episodic and Continuing Tasks
- **Episodic Tasks**: Defined beginning and end (e.g., a game of chess, pole balancing before falling).
- **Continuing Tasks**: Continue indefinitely without a natural endpoint (e.g., stock market trading).
- **Unified notation**: Uses a discount factor \(\gamma\) to handle both cases:
  - For episodic tasks, \(\gamma\) may be set to 1 or a terminating state is defined.
  - For continuing tasks, \(\gamma < 1\) ensures that future rewards diminish over time.

### 3. Policies and Value Functions
- **Policy** \(\pi(s)\): Defines the action selection strategy.
- **State-value function** \(V_{\pi}(s)\): Estimates the expected return when following policy \(\pi\) from state \(s\).
- **Action-value function** \(Q_{\pi}(s, a)\): Estimates the expected return when taking action \(a\) in state \(s\) and then following policy \(\pi\).

### 4. Optimal Policies and Optimal Value Functions
- **Optimal policy** \(\pi^*\): Maximizes the expected return from any state.
- **Optimal value function** \(V^*(s)\): Gives the highest possible return from any state \(s\).
- **Optimal action-value function** \(Q^*(s, a)\): Determines the best possible return for state-action pairs.

### 5. Optimality and Approximation
- Exact optimal solutions (e.g., via dynamic programming) are feasible only for small problems.
- Approximate methods, such as Deep Q-Networks (DQN) and policy gradient methods, are used in large or continuous state spaces.
- **Function approximation** (e.g., using neural networks) generalizes learning across states where exact tabular methods fail.

---

This README provides an overview of the CartPole problem and its relevance in reinforcement learning. The topics covered include random policies, episodic vs. continuing tasks, policies and value functions, and optimality with approximations. Understanding these concepts is fundamental to designing and implementing RL solutions efficiently.

