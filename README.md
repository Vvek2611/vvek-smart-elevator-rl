# Smart Elevator Control System using Reinforcement Learning

MSc Project — Tabular Q-Learning applied to elevator dispatch optimization.

## Demo
Live: https://vvek2611.github.io/vvek-smart-elevator-rl

## Problem Formulation
- **State**: floor, direction, 5 binary call/passenger flags
- **Actions**: {stay/open doors, move up, move down}
- **Reward**: +15 delivered, +5 picked up, −0.5/move, −0.25/waiting passenger

## Algorithm
Tabular Q-Learning with ε-greedy exploration (ε decays 1.0 → 0.04)

## Results
Agent learns SCAN-like policy within ~150 episodes.

## Run Locally
Just open index.html in a browser — no dependencies.
