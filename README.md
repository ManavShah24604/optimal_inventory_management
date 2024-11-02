

# Inventory Management with Reinforcement Learning

This project tackles the **Inventory Management Problem** using various **Reinforcement Learning (RL)** techniques to help retail stores maintain optimal stock levels and minimize associated costs. Effective inventory control is crucial for balancing holding costs, procurement costs, and backlogs in response to unpredictable customer demand.

## Problem Overview

Retail stores regularly replenish their inventory to meet customer demand, which varies randomly. The store needs to determine the optimal stock to purchase each period to minimize the total expected costs, which include:
1. **Purchase Cost**: Cost per unit of newly purchased stock.
2. **Holding Cost**: Cost per unit for holding excess stock.
3. **Backlog Cost**: Cost incurred when there is insufficient stock to meet demand.

The demand varies, making it necessary to develop an optimal policy that balances these costs over a specified time horizon.

### Key Variables and Objectives

- **Inventory Level** \(X_t\): The stock level before each procurement.
- **Procurement Decision** \(U_t\): Additional stock purchased at each time step, up to a maximum limit.
- **Demand \(W_t\)**: A randomly generated demand, modeled as an independent and identically distributed variable.
- **Objective**: Minimize the expected total cost over a finite time period by optimizing the inventory procurement policy.

## Approaches

We explored several RL algorithms to determine optimal strategies:

1. **Value Iteration**:
   - A dynamic programming method that iterates over possible actions to find the lowest cost for each state.
   - Experiments were conducted with various parameters to identify optimal policies under different cost structures.

2. **Policy Iteration**:
   - Another dynamic programming method that refines a policy by evaluating its performance and updating it iteratively.

3. **Monte Carlo Control (MC)**:
   - A simulation-based approach that uses cumulative episodes to evaluate policies. MC control does not require a model of the environment, making it adaptable for learning from experience.

4. **TD Control with SARSA(λ)**:
   - A temporal difference learning method that combines ideas from dynamic programming and Monte Carlo methods.
   - Due to its dependency on temporal factors, the SARSA(λ) approach here was adjusted for finite-horizon scenarios.

5. **Q-Learning**:
   - A model-free RL method that iterates through state-action pairs to learn optimal actions.
   - The Q-learning approach used here is based on stochastic approximation, providing stability and convergence.

### Parameter Testing

For each method, we tested a range of values to observe their effects on performance. Key parameters included:
- **Holding Cost (a)**, **Backlog Cost (b)**, and **Purchase Cost (p)**.
- **State and Action Spaces**: The range of inventory levels and potential procurement decisions.
- **Demand Distribution**: Various distributions for demand were tested to simulate real-world uncertainty.

## Results and Evaluation

Each algorithm was evaluated using:
- **Instantaneous Regret**: The difference between the cost at each step and the theoretical optimal cost.
- **Cumulative Regret**: The total accumulated regret, which gives insight into the long-term performance.
- **Policy Stability**: Measured through convergence in dynamic programming-based methods.


## Conclusion

This project demonstrates the feasibility of using RL to tackle inventory management problems. Each method provided valuable insights, and the tested policies offer frameworks that retail stores can adapt to optimize their stock levels effectively.
