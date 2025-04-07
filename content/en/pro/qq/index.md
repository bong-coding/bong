---
title: Pacman AI (In Progress)
date: 2025-04-02
---
### 🔗 https://github.com/bong-coding/pacman
# Building AI Agents to Control Pacman
**A hands-on project focused on implementing core AI concepts**
---



## 💡 Key Learning Topics

### ✔️ Search Algorithms
- DFS / BFS / UCS / A*  
- Game tree search (Minimax, Alpha-Beta Pruning)

### ✔️ Markov Decision Processes (MDP)
- Value Iteration, Policy Iteration

### ⏳ Probability & Inference
- Bayes Rule, Hidden Markov Models (HMM), Particle Filtering

### ⏳ Reinforcement Learning
- Q-learning, Exploration vs Exploitation

### ⏳ Machine Learning Fundamentals
- Naive Bayes, Perceptron, Intro to Neural Networks

---

## 📂 Project Overview

| Project | Description |
|---------|-------------|
| **Project 1: Search** | Implemented DFS, BFS, UCS, A* for Pacman maze navigation |
| **Project 2: Multi-Agent** | Developed strategic agents using Minimax, Expectimax, Alpha-Beta Pruning |
| **Project 3: MDPs** | Built GridWorld with Value Iteration and Policy Iteration |
| **Project 4: Reinforcement Learning** | Created a Q-learning based learning agent |
| **Project 5: Classification** | Handwriting classifier using Naive Bayes and Perceptron |
| **Project 6 (Optional): Neural Nets** | (Unofficial) Simple image classifier using basic DNN |

---

## 🗂️ Project Structure

```bash
.
├── pacman.py               # Main game engine
├── search.py               # DFS, BFS, UCS, A* implementations
├── searchAgents.py         # Agents utilizing search algorithms
├── game.py                 # Core game logic (agents, environment)
├── ghostAgents.py          # AI logic for ghosts
├── pacmanAgents.py         # Basic Pacman agents (e.g., GreedyAgent)
├── eightpuzzle.py          # 8-puzzle problem for search testing
├── layout.py               # Handles map layouts
├── graphicsDisplay.py      # GUI rendering logic
├── textDisplay.py          # CLI-based rendering
├── graphicsUtils.py        # Helper functions for graphics
├── util.py                 # Shared data structures and utilities
├── projectParams.py        # Global project parameters
├── grading.py              # Auto-grading logic
├── autograder.py           # Script to run all test cases
├── testClasses.py          # Unit testing classes
├── testParser.py           # Test file parser
└── searchTestClasses.py    # Test classes for search problems

```
---

## 🛠️ Environment & Requirements

- Python 3.x
- Numpy
- Basic command-line familiarity
- (Optional) VS Code or PyCharm for development
---

### ▶️ How to Run

Run the basic game
```bash
python pacman.py
```
Run with a specific layout:
```bash
python pacman.py -l mediumClassic
```
Run with a specific agent (e.g., DFS):
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=depthFirstSearch
```
Run A* algorithm with heuristic:
```bash
python pacman.py -l mediumMaze -p SearchAgent -a fn=aStarSearch,heuristic=manhattanHeuristic
```