# Reinforcement Learning using MDP – Value Iteration

A simple implementation of **Reinforcement Learning using a Markov Decision Process (MDP)** with the **Value Iteration algorithm** and **Bellman Equation** in Python.

The project uses a 4×4 grid environment where an agent starts from a starting position, avoids an obstacle, and learns the optimal path to reach the goal.

## 📌 Project Overview

This project demonstrates how an agent can determine the **optimal policy** for navigating through a grid using Value Iteration.

The agent can perform four actions:

* ↑ UP
* ↓ DOWN
* ← LEFT
* → RIGHT

The environment contains:

* `S` → Starting State
* `G` → Goal State
* `X` → Obstacle
* `.` → Normal State

### Grid Environment

```text
S  .  .  .
.  X  .  .
.  .  .  .
.  .  .  G
```

The agent starts at `S` and must reach `G` while avoiding the obstacle `X`.

## 🧠 Concepts Used

This project implements the following Reinforcement Learning concepts:

* Markov Decision Process (MDP)
* States
* Actions
* Reward Function
* Transition Function
* Discount Factor
* Bellman Equation
* Bellman Optimality Equation
* Value Iteration
* Optimal Policy

## ⚙️ Reward Function

The reward system used in this environment is:

| Situation         | Reward |
| ----------------- | -----: |
| Reaching the Goal |  `+10` |
| Normal Movement   |   `-1` |

The negative reward for movement encourages the agent to find a shorter path to the goal.

## 🔄 Transition Function

The transition function determines the next state after an action.

The agent:

* Cannot move outside the grid.
* Cannot move through the obstacle.
* Remains in the same state if an invalid movement is attempted.

## 📐 Bellman Equation

The project uses the Bellman equation:

```text
V(s) = R(s,a) + γV(s')
```

Where:

* `V(s)` = Value of the current state
* `R(s,a)` = Reward received after taking an action
* `γ` = Discount factor
* `V(s')` = Value of the next state

The discount factor used in this project is:

```python
gamma = 0.9
```

## 🔁 Value Iteration

Value Iteration repeatedly updates the value of each state using the Bellman Optimality Equation:

```text
V(s) = max [ R(s,a) + γV(s') ]
```

For every state, the algorithm checks all possible actions and selects the action that produces the highest expected value.

In this implementation, the algorithm runs for:

```python
iterations = 20
```

## 🎯 Optimal Policy

After calculating the state values, the program extracts the optimal action for every state.

The policy is displayed using arrows:

```text
↑  UP
↓  DOWN
←  LEFT
→  RIGHT
G  GOAL
X  OBSTACLE
```

A typical optimal policy will guide the agent from the starting position toward the goal while avoiding the obstacle.

## 🛠️ Technologies Used

* **Python**
* **NumPy**
* **Reinforcement Learning**
* **Markov Decision Process (MDP)**
* **Value Iteration**
* **Bellman Equation**

## 📦 Installation

Make sure Python is installed on your system.

Install NumPy using:

```bash
pip install numpy
```

## ▶️ How to Run

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```

Navigate to the project directory:

```bash
cd YOUR-REPOSITORY
```

Run the Python file:

```bash
python filename.py
```

The program will display:

1. Available states
2. Available actions
3. Calculated state values
4. Optimal policy

## 📊 Example Output

### State Values

The program generates a value for each valid state:

```text
State Values:
----------------
[...., ...., ...., ....]
[....,  X , ...., ....]
[...., ...., ...., ....]
[...., ...., ...., 0.00]
```

The exact values depend on the number of Value Iteration steps.

### Optimal Policy

The final policy is represented using arrows:

```text
→  →  →  ↓
↑  X  →  ↓
→  →  →  ↓
→  →  →  G
```

The arrows represent the best action selected by the Value Iteration algorithm.

## 🚀 Future Improvements

This project can be extended by adding:

* Stochastic transitions
* Different reward values
* Multiple obstacles
* Multiple goal states
* Larger grid environments
* Q-Learning
* SARSA
* Random starting positions
* Visualization using Matplotlib
* Interactive grid environment

## 📚 Learning Objective

The main objective of this project is to understand how **Reinforcement Learning agents can use MDPs and Value Iteration to determine optimal actions**.

It provides a simple practical example of how the **Bellman Equation** is used to calculate state values and derive an optimal policy.

## 👨‍💻 Author

**Shubham Londhe**

GitHub: `https://github.com/Shubham-007-debug`
