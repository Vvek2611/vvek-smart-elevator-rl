 🛗 Smart Elevator Dispatch System using Reinforcement Learning.
 
 URL: https://Vvek2611.github.io/vvek-smart-elevator-rl
 
📌 Project Overview:
An interactive browser-based simulation of a Q-Learning agent learning to optimally control elevator
dispatch — built as an MSc project in Artificial Intelligence & Reinforcement Learning.

📌 Purpose:
Traditional elevator dispatch algorithms (SCAN, LOOK, Nearest-Car) rely on hand-crafted heuristics.
This project explores whether a **Reinforcement Learning agent** can learn an optimal dispatch policy **from scratch** —
with no prior knowledge — purely through trial and error interaction with the environment.

The agent starts completely random and gradually learns to:
- Serve passengers already on the elevator before moving
- Avoid unnecessary floor reversals
- Minimize total passenger waiting time
- Balance exploration vs exploitation over time
  
  ✨ Features:
**Live Building Simulation** — Animated elevator shaft showing elevator position, door state, direction, onboard passengers, and waiting passengers per floor in real time
**Q-Value Heatmap** — Live table showing the learned policy: green = agent prefers this action, red = agent avoids this action, per floor
**Reward History Chart** — Episode-by-episode reward curve with 10-episode rolling average showing learning progress
**Adjustable Hyperparameters** — Tune learning rate (α), discount factor (γ), number of floors (4–12), and simulation speed live via sliders
**Episode Progress Bar** — Visual indicator of current episode progress (200 steps/episode)
**Live Metrics Dashboard** — Episode count, episode reward, total deliveries, average wait time, current ε value, number of Q-states discovered
**Step-by-step Mode** — Single-step button for educational walkthroughs
**Pause / Resume** — Full control over training speed
**Zero Dependencies** — Runs entirely in the browser, no install needed

  🧠 Algorithm Deep Dive:
  Agent Class: `ElevatorAgent`
```javascript
class ElevatorAgent {
  constructor(n)       // n = number of floors
  state()              // encodes current MDP state as string key
  act(s)               // ε-greedy action selection
  step()               // execute one timestep, update Q-table
  endEpisode()         // decay ε, return episode stats
}

🔐 Authentication:

This is a client-side academic simulation with no backend, no user data, no login, and no API keys. Everything runs locally in the browser.
  
 📊 Results:

After ~150–200 training episodes the agent consistently learns:

1. **Service current floor first** — open doors if passengers waiting or to be dropped off
2. **Directional continuity** — continue moving in one direction before reversing (mirrors SCAN algorithm)
3. **Idle positioning** — return to ground floor when no calls pending
4. **Reward improvement** — episode reward increases from ~−50 (random) to ~+80 (trained)

👤 Author:

**Vvek**  
MSc Student — Computer Science / Artificial Intelligence  
GitHub: [@Vvek2611](https://github.com/Vvek2611)
