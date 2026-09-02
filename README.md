# 🚚 RL-ACO Study: Stochastic Scheduling & Routing

An applied study reproducing and analyzing a Q-learning + Ant Colony Optimization (ACO) 
approach to the **Stochastic Home Health Care Scheduling and Routing Problem (SHHCSRP)**, 
a combinatorial variant of the Vehicle Routing Problem.

## 📋 Overview

This repository documents my exploration of applying reinforcement learning to a 
large-scale stochastic combinatorial optimization problem. The task: assign demands 
from multiple customers to a set of vehicles at minimized cost, learned via a 
Q-learning agent operating over a hierarchical MDP.

🔎 This is a **study/reproduction project**, based on the original implementation and 
research by Ian Yang Chin ([source repo](https://github.com/IanYangChina/SHHCSRP)). 
My focus was on understanding, running, debugging, and critically evaluating the 
approach — not on novel algorithmic contribution.

## 🛠️ What I did

- 🔁 Reproduced the Q-learning + ACO hybrid across the provided problem instances
- 🧩 Traced the hierarchical MDP/CCP formulation: state representation, action selection 
  (vehicle assignment), and reward computation
- 🐛 Debugged the training loop and ACO-based routing solver to understand their interaction
- 📊 Evaluated generated solutions and analyzed why performance fell short of consistent 
  optimality
- 🔍 Identified the same core limitations documented by the original author — insufficient 
  state abstraction and reward shaping — and reasoned through why they matter for RL 
  applied to combinatorial problems

## 💡 Key takeaway

Classical tabular RL methods (Q-learning) struggle on large, stochastic combinatorial 
search spaces without careful state representation and reward design — this project 
was a hands-on look at **why**, using routing/scheduling as the test case.

## 🙏 Credit

Original implementation and problem formulation: 
[IanYangChina/SHHCSRP](https://github.com/IanYangChina/SHHCSRP)

## 📁 Files
| File | Description |
|---|---|
| `QL_BWACO.py` | Q-learning + ACO algorithm implementation |
| `main.py` | Entry point for running experiments |
| `*.xlsx` | Problem instance data |
| `*.csv` | Initial preference settings |

## ▶️ Run
1. ⚙️ Configure the experiment instance and vehicle resources at the top of `__main__`
2. ▶️ Run `python main.py`
3. 📈 Outputs (solution plots and result files) are written to the root folder
