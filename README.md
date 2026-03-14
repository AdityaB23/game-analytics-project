![Game Analytics Banner](plots/game_health_dashboard.png)

# Game Analytics Case Study
### Difficulty, Player Behavior & Game Economy Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Analytics](https://img.shields.io/badge/Domain-Game%20Analytics-purple)
![Status](https://img.shields.io/badge/Project-Portfolio-green)

Analytics case study demonstrating how gameplay telemetry can be used to detect difficulty spikes, player frustration, and churn risk in level-based puzzle games.

# Quick Start

git clone https://github.com/AdityaB23/game-analytics-project.git  
cd game-analytics-project  

pip install -r requirements.txt  

python src/telemetry_generator.py  

streamlit run dashboard/app.py
---

# Project Preview

| Difficulty Curve | Player Retention | Level Health |
|---|---|---|
| ![](plots/difficulty_curve.png) | ![](plots/retention_curve.png) | ![](plots/level_health_chart.png) |

---

# Contents

- Hiring Manager TL;DR
- Project Motivation
- Executive Summary
- Game Health Dashboard
- Interactive Dashboard
- Project Overview
- Dataset
- Analytics Workflow
- Visualizations
- Game Designer Takeaways
- Case Study Reports
- Repository Structure
- Setup

---

# Hiring Manager TL;DR

This project analyzes gameplay telemetry from a simulated puzzle game to detect **difficulty spikes and player churn risk**.

Using telemetry for **~3000 players across 120 levels**, the analysis identifies a **major progression bottleneck around Level 50**.

| Metric | Observation |
|------|-------------|
| Win Rate | ~42% |
| Average Attempts | ~5.6 |
| Churn Probability | ~21% |

These signals indicate **player frustration and progression drop-off**.

The project demonstrates:

- gameplay telemetry analytics
- difficulty spike detection
- A/B experiment simulation
- churn prediction modeling
- game economy analysis
- analytics dashboard

---

# Project Motivation

Balancing difficulty is a core challenge in live-operated puzzle games.

If levels are too easy:

- players lose engagement

If levels are too difficult:

- players become frustrated and churn.

Game analytics teams use telemetry to monitor **player experience and progression bottlenecks**.

This project demonstrates how gameplay telemetry can support **data-driven difficulty tuning**.

---

# Executive Summary

Three gameplay signals are analyzed:

| Metric | Meaning |
|------|------|
| Win Rate | level difficulty |
| Retry Rate | player frustration |
| Churn Probability | player drop-off |

The analysis identifies a **mid-game difficulty spike** where:

- win rates decrease
- retry attempts increase
- churn rises

Simulation experiments suggest **booster rewards after repeated failures** improve progression.

---

# Game Health Dashboard

![](plots/game_health_dashboard.png)

This dashboard combines:

- win rate
- retry behavior
- churn probability

to detect **progression bottlenecks**.

---

# Interactive Dashboard

Run locally:

```bash
streamlit run dashboard/app.py
```

The dashboard allows interactive exploration of:

- difficulty curves
- retry behavior
- player progression
- difficulty alerts

---

# Project Overview

This repository demonstrates a full analytics workflow for **live game operations**.

Capabilities demonstrated:

- telemetry analytics
- player behavior modeling
- experimentation analysis
- churn prediction
- economy balancing
- analytics dashboards

Dataset scale:

- ~3000 simulated players  
- ~120 levels  
- ~200k gameplay events  

---

# Dataset

Gameplay telemetry is generated using:

```bash
python src/telemetry_generator.py
```

Example schema:

| Feature | Description |
|------|-------------|
| player_id | player identifier |
| level | level number |
| attempt | retry count |
| win | level completion |
| boosters_used | boosters used |

---

# Analytics Workflow

1. Generate gameplay telemetry  
2. Analyze level difficulty  
3. Identify difficulty spikes  
4. Simulate gameplay experiments  
5. Predict player churn  
6. Analyze virtual economy  

---

# Visualizations

### Difficulty Curve

![](plots/difficulty_curve.png)

### Player Retention

![](plots/retention_curve.png)

### Level Health Chart

![](plots/level_health_chart.png)

### Transition Heatmap

![](plots/transition_heatmap.png)

---

# Game Designer Takeaways

### Smooth Mid-Game Difficulty

Telemetry shows a **difficulty spike around levels 45–55**.

Target:

```
70–80% win rate
```

Possible changes:

- increase available moves
- simplify board layouts
- reduce blocker density

---

### Introduce Failure Recovery Mechanics

Players experiencing repeated failures are more likely to churn.

Possible interventions:

- booster rewards after retries
- extra moves
- temporary bonuses

---

# Case Study Reports

Included reports:

```
report/game_analytics_full_report.pdf
report/game_analytics_case_study_level50.pdf
```

These demonstrate how analytics insights can be communicated to **game design teams**.

---

# Repository Structure

```
game-analytics-project
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── data
│
├── notebooks
│   01_level_difficulty_analysis.ipynb
│   02_experiment_design_and_ab_testing.ipynb
│   03_game_economy_analysis.ipynb
│
├── src
│   telemetry_generator.py
│   difficulty_monitor.py
│   churn_model.py
│
├── dashboard
│   app.py
│
├── plots
│
└── report
```

---

# Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

Generate telemetry dataset:

```bash
python src/telemetry_generator.py
```

Launch dashboard:

```bash
streamlit run dashboard/app.py
```

---

# Author

Aditya Bawane  

Game Analytics Portfolio
