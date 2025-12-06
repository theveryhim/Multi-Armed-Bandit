# Multi-Armed Bandits Homework

### Overview
This notebook implements and empirically compares several classic action-value methods for the k-armed bandit problem (k=10) as described in Sutton & Barto (2nd ed.), Chapter 2.

All experiments use:
- 2000 independent runs
- 1000 time steps per run
- Gaussian reward noise (σ²=1)

### Tasks

#### Incremental Value Estimation & Step-Size Effects  
- ε-greedy (ε=0.1) with sample-average and constant step-sizes α ∈ {0.05, 0.1, 0.2, 0.4}
- Tested on both **stationary** and **non-stationary** (random walk σ=0.01) bandits
- Shows why sample-averages work best when the environment is stationary and why larger constant α is required for tracking non-stationary problems.

#### Exploration-Exploitation Trade-off with ε-Greedy  
- Comparison of ε = 0, 0.01, 0.1 (sample-average updates)
- Demonstrates that pure greedy (ε=0) gets stuck on suboptimal arms while moderate exploration (ε≈0.1) yields the highest long-term reward.

#### Upper Confidence Bound (UCB) vs ε-Greedy  
- ε-greedy (ε=0.1) vs UCB with c = 1 and c = 1.25 (or 2.5 in some runs)
- Plots average reward, % optimal action, and **cumulative regret** (log scale)
- UCB clearly outperforms ε-greedy by achieving lower regret through optimism in the face of uncertainty.

#### Gradient Bandit Algorithm  
- Softmax action preferences with/without average-reward baseline
- α = 0.1 and α = 0.4
- Baseline dramatically reduces variance and improves performance, especially for larger step-sizes.

### Results (insert images below)

| Task | Average Reward | % Optimal Action | Cumulative Regret (Task 3) |
|------|----------------|------------------|----------------------------|
| 1 – Stationary | ![Task1-stationary-reward](figures/task1_stationary_reward.png) | ![Task1-stationary-optimal](figures/task1_stationary_optimal.png) | – |
| 1 – Non-stationary | ![Task1-nonstationary-reward](figures/task1_nonstationary_reward.png) | ![Task1-nonstationary-optimal](figures/task1_nonstationary_optimal.png) | – |
| 2 – ε comparison | ![Task2-reward](figures/task2_reward.png) | ![Task2-optimal](figures/task2_optimal.png) | – |
| 3 – UCB vs ε-greedy | ![Task3-reward](figures/task3_reward.png) | ![Task3-optimal](figures/task3_optimal.png) | ![Task3-regret](figures/task3_regret_log.png) |
| 4 – Gradient bandit | ![Task4-reward](figures/task4_reward.png) | ![Task4-optimal](figures/task4_optimal.png) | – |

**Note that results are discussed in the notebook!**
