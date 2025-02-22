
# Value Iteration on the Gambler's Problem

## Problem Definition
The **Gambler’s Problem** is a classic reinforcement learning problem where a gambler makes bets to maximize their probability of reaching a goal amount. The problem is defined as follows:

- The gambler starts with a capital **s** between **0** and **100**.
- The goal is to reach **100** units.
- At each step, the gambler can bet an amount **a**, where:
  
  \[ 0 \leq a \leq \min(s, 100-s) \]
  
- If the bet wins, the gambler gains **a**; if it loses, they lose **a**.
- The probability of winning each bet is **p_h** (e.g., **0.4**).

## Bellman Equation
The state-value function is given by:

\[ V(s) = \max_{a} \left[ p_h V(s + a) + (1 - p_h) V(s - a) \right] \]

where:
- \( V(s) \) is the value of being in state **s**.
- \( p_h \) is the probability of winning.
- \( V(0) = 0 \) (gambler loses everything).
- \( V(100) = 1 \) (gambler reaches the goal).

## Value Iteration Algorithm

1. **Initialize** \( V(s) = 0 \) for all states except \( V(100) = 1 \).
2. **Iterate** until convergence:
   - For each state \( s \), update:
     
     \[ V(s) \leftarrow \max_{a} \left[ p_h V(s + a) + (1 - p_h) V(s - a) \right] \]
     
   - Keep track of the optimal action \( a^* \) at each state.
3. **Extract Policy**: For each \( s \), find the bet \( a^* \) that maximizes the expected value.

## Python Implementation

## Results
1. **Value Function**: Shows the probability of reaching **100** from each capital.
2. **Optimal Policy**: Shows the best bet at each capital level.

## Observations
- The optimal policy is **deterministic**, meaning there is a unique best action for each **s**.
- The policy depends on **p_h**; a higher **p_h** encourages larger bets.
- Value iteration converges quickly since it is a finite-state problem.

This approach efficiently finds the best strategy for maximizing the probability of reaching the goal in the **Gambler’s Problem**. 🚀

