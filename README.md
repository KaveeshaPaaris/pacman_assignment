# 🟡 Pacman AI — Search Algorithms (Project 1)

> **UC Berkeley CS188** · Project 1: Search  
> Implementing classic AI search algorithms to navigate Pacman through mazes.

---

## 📋 Overview

This project implements **four core search algorithms** used by Pacman agents to find optimal paths through maze layouts. The algorithms are applied to increasingly complex problems — from simple point-to-point navigation to collecting all food dots on the board.

**Files modified:**
- [`search.py`](search.py) — Core search algorithm implementations
- [`searchAgents.py`](searchAgents.py) — Search problem definitions and heuristics

---

## 🧠 Algorithms Implemented

| Algorithm | Function | Data Structure | Optimality |
|-----------|----------|---------------|------------|
| Depth-First Search | `depthFirstSearch` | Stack | ✗ No |
| Breadth-First Search | `breadthFirstSearch` | Queue | ✓ Yes (uniform cost) |
| Uniform Cost Search | `uniformCostSearch` | Priority Queue | ✓ Yes |
| A\* Search | `aStarSearch` | Priority Queue | ✓ Yes (admissible heuristic) |

---

## 🗂️ Project Structure

```
pacman_assignment/
├── search.py           # ★ DFS, BFS, UCS, A* implementations
├── searchAgents.py     # ★ CornersProblem, FoodSearchProblem, heuristics
├── pacman.py           # Game engine & CLI entry point
├── game.py             # Core game logic (Agent, Directions, Actions)
├── util.py             # Stack, Queue, PriorityQueue, manhattanDistance
├── ghostAgents.py      # Ghost behaviour
├── keyboardAgents.py   # Human-playable keyboard agent
├── graphicsDisplay.py  # GUI renderer
├── autograder.py       # Automated grading script
├── layouts/            # 37 maze layout files (.lay)
└── test_cases/         # Test cases for autograder
```

---

## 🚀 Getting Started

### Prerequisites

- Python **3.x**

### Play the game (keyboard)

```bash
python pacman.py
```
Use **arrow keys** or `W A S D` to move.

---

## 🔬 Running Search Agents

### Depth-First Search
```bash
python pacman.py -p SearchAgent -a fn=dfs
python pacman.py -p SearchAgent -a fn=dfs,prob=PositionSearchProblem -l mediumMaze
```

### Breadth-First Search
```bash
python pacman.py -p SearchAgent -a fn=bfs
python pacman.py -p SearchAgent -a fn=bfs -l mediumMaze
```

### Uniform Cost Search
```bash
python pacman.py -p SearchAgent -a fn=ucs
python pacman.py -p SearchAgent -a fn=ucs -l mediumMaze
```

### A\* Search (with Manhattan heuristic)
```bash
python pacman.py -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic
python pacman.py -p SearchAgent -a fn=astar,heuristic=manhattanHeuristic -l bigMaze
```

---

## 🧩 Search Problems

### Corners Problem
Find a path that visits all **four corners** of the maze.
```bash
python pacman.py -l tinyCorners -p SearchAgent -a fn=bfs,prob=CornersProblem
python pacman.py -l mediumCorners -p SearchAgent -a fn=astar,prob=CornersProblem,heuristic=cornersHeuristic
```

### Food Search Problem
Collect **all food dots** on the board.
```bash
python pacman.py -l testSearch -p AStarFoodSearchAgent
python pacman.py -l trickySearch -p AStarFoodSearchAgent
```

---

## 🏃 Common Options

| Flag | Description | Example |
|------|-------------|---------|
| `-l <layout>` | Choose a map layout | `-l bigMaze` |
| `-p <agent>` | Choose a Pacman agent | `-p SearchAgent` |
| `-a fn=<algo>` | Choose search function | `-a fn=astar` |
| `-z <zoom>` | Zoom the display | `-z 2` |
| `-q` | Quiet mode (no graphics) | `-q` |
| `-n <N>` | Run N games | `-n 3` |

---

## ✅ Autograder

Run the full test suite:
```bash
python autograder.py
```

Run a specific question:
```bash
python autograder.py -q q1   # DFS
python autograder.py -q q2   # BFS
python autograder.py -q q3   # UCS
python autograder.py -q q4   # A*
python autograder.py -q q5   # Corners Problem
python autograder.py -q q6   # Corners Heuristic
python autograder.py -q q7   # Food Heuristic
```

---

## 📜 Attribution

This project is based on the [UC Berkeley Pacman AI Projects](http://ai.berkeley.edu), developed by:
- **John DeNero** (denero@cs.berkeley.edu)
- **Dan Klein** (klein@cs.berkeley.edu)
- **Brad Miller, Nick Hay, Pieter Abbeel** (autograder)

> Free to use or extend for **educational purposes** only.  
> Do not distribute or publish solutions.
