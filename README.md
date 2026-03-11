# Game Analytics Case Study
### Level Difficulty, Player Behavior & Game Economy Analysis

![Python](https://img.shields.io/badge/Python-3.10-blue)
![Analytics](https://img.shields.io/badge/Domain-Game%20Analytics-purple)
![Status](https://img.shields.io/badge/Project-Portfolio-green)

Analytics case study demonstrating how gameplay telemetry can be used to detect **difficulty spikes, player frustration, and churn risk** in level-based puzzle games.

Inspired by analytics workflows used in live-operated puzzle games such as Candy Crush–style games.

---

# Project Preview

| Difficulty Curve | Player Retention | Game Health Dashboard |
|---|---|---|
| ![Difficulty](plots/difficulty_curve.png) | ![Retention](plots/retention_curve.png) | ![Dashboard](plots/game_health_dashboard.png) |

---

### Level Health Chart

![Level Health](plots/level_health_chart.png)

This chart combines **difficulty, retry behavior, and churn probability** to detect gameplay bottlenecks.

---

# Contents

- [Hiring Manager TL;DR](#-hiring-manager-tldr)
- [Project Motivation](#project-motivation)
- [Executive Summary](#executive-summary)
- [Game Health Dashboard](#game-health-dashboard)
- [Interactive Analytics Dashboard](#interactive-analytics-dashboard)
- [Project Overview](#project-overview)
- [Gameplay Telemetry](#gameplay-telemetry)
- [Analytics Workflow](#analytics-workflow)
- [Visualizations](#visualizations)
- [Game Designer Takeaways](#game-designer-takeaways)
- [Case Study Reports](#case-study-reports)
- [Difficulty Monitoring Script](#difficulty-monitoring-script)
- [Repository Structure](#repository-structure)

---

# 🎮 Hiring Manager TL;DR

This project analyzes gameplay telemetry from a simulated puzzle game to detect **difficulty spikes and player churn risk**.

Using telemetry for **~3000 players across 120 levels**, the analysis identifies a **major progression bottleneck around Level 50**.

| Metric | Observation |
|------|-------------|
| Win Rate | ~42% |
| Average Attempts | ~5.6 retries |
| Churn Probability | ~21% |

These signals indicate **player frustration and progression drop-off**.

Key capabilities demonstrated:

- telemetry simulation (~200k gameplay events)
- difficulty spike detection
- player retention modeling
- churn prediction
- Monte Carlo progression simulation
- A/B testing simulation
- game economy analysis
- automated difficulty monitoring
- interactive analytics dashboard

---

# Project Motivation

Balancing difficulty is a core challenge in live-operated puzzle games.

If levels are too easy:

- players lose engagement

If levels are too difficult:

- players become frustrated and churn.

Game analytics teams use gameplay telemetry to monitor player experience and detect progression bottlenecks.

This project demonstrates how telemetry analytics can support **data-driven difficulty tuning and player retention optimization**.

---

# Executive Summary

Balancing difficulty is one of the most important challenges in live-operated puzzle games.

Three gameplay signals are analyzed:

| Metric | Meaning |
|------|------|
| Win Rate | Level difficulty |
| Retry Rate | Player frustration |
| Churn Probability | Player drop-off |

The analysis identifies a **mid-game difficulty spike** where:

- win rates decrease sharply
- retry attempts increase
- player churn rises

Simulation experiments suggest that **booster rewards after repeated failures** can significantly improve player progression.

---

# Game Health Dashboard

This dashboard combines three gameplay signals:

- **Win Rate → Difficulty**
- **Retry Rate → Frustration**
- **Churn Probability → Player Drop-Off**

![Game Health Dashboard](plots/game_health_dashboard.png)

When all three metrics spike simultaneously, the level likely creates **player frustration and progression bottlenecks**.

---

# Interactive Analytics Dashboard

The project includes a **Streamlit dashboard** for exploring gameplay telemetry.

Run locally:

```bash
streamlit run dashboard/app.py
```

The dashboard enables interactive exploration of:

- difficulty curves
- retry behavior
- player progression
- difficulty spike alerts

---

# Project Overview

This repository demonstrates a full analytics workflow for **live game operations**.

Capabilities demonstrated:

- gameplay telemetry analytics
- difficulty spike detection
- player retention modeling
- churn prediction
- experiment simulation
- economy balance analysis
- automated difficulty monitoring
- analytics dashboards

Dataset scale:

```
~3000 simulated players
~120 levels
~200k gameplay events
```

---

# Gameplay Telemetry

Each row represents a player attempting a level.

| Feature | Description |
|------|-------------|
| player_id | unique player identifier |
| level | level number |
| attempt | retry count |
| win | level completion |
| boosters_used | boosters used |

Example:

| player_id | level | attempt | win | boosters_used |
|------|------|------|------|------|
| 102 | 12 | 2 | 1 | 0 |
| 102 | 13 | 4 | 0 | 1 |

---

# Analytics Workflow

## 1. Difficulty Analysis

Win rate across levels reveals difficulty spikes.

Puzzle games typically target:

```
70–80% win rate
```

Levels far below this range often cause **player frustration**.

---

## 2. Retry Behavior

Retry rate measures **player frustration**.

High retries indicate:

- confusing mechanics
- excessive difficulty
- lack of progression tools

---

## 3. Player Progression Funnel

Player retention is measured through **maximum level reached**.

Large drops indicate **progression bottlenecks**.

---

## 4. Difficulty Spike Detection

Composite difficulty score:

```
difficulty_score = avg_attempts × (1 − win_rate)
```

Levels with high scores likely require **design adjustments**.

---

## 5. Monte Carlo Progression Simulation

Simulation estimates expected player progression under different difficulty conditions.

Insight:

> Difficulty spikes significantly reduce expected progression depth.

---

## 6. Churn Prediction

A Random Forest model predicts player churn using gameplay behavior.

Key features:

- win rate
- retry attempts
- booster usage

---

## 7. Experiment Simulation

A simulated A/B test evaluates a gameplay intervention.

Treatment:

```
Free booster after repeated failures
```

Results show **improved player progression**.

---

# Visualizations

### Difficulty Curve

![Difficulty Curve](plots/difficulty_curve.png)

### Player Retention Funnel

![Retention Curve](plots/retention_curve.png)

### Churn Probability

![Churn Curve](plots/churn_probability.png)

### Level Transition Heatmap

![Transition Heatmap](plots/transition_heatmap.png)

---

# Game Designer Takeaways

### Smooth Mid-Game Difficulty

Telemetry shows a **difficulty spike around levels 45–55**.

| Metric | Observation |
|------|-------------|
| Win Rate | drops below target range |
| Retry Rate | increases |
| Churn Probability | peaks afterward |

Target:

```
Restore win rate to ~70–80%
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
- temporary move bonuses
- extra lives

---

### Monitor Retry Rate

Retry rate often increases **before churn**, making it an early warning signal.

---

# Case Study Reports

Example gameplay analytics reports included in this repository:

- `report/game_analytics_full_report.pdf`
- `report/game_analytics_case_study_level50.pdf`

These reports demonstrate how analytics insights can be communicated to **game designers and product teams**.

---

# Difficulty Monitoring Script

An automated monitoring tool flags problematic levels.

Run:

```
python src/difficulty_monitor.py
```

Example output:

```
Level 50
Win Rate: 0.42
Avg Attempts: 5.6
Churn Probability: 0.21
```

---

# Repository Structure

```
game-analytics-project
│
├── data
│   gameplay.csv
│
├── notebooks
│   level_difficulty_analysis.ipynb
│   experiment_design_and_ab_testing.ipynb
│   game_economy_analysis.ipynb
│
├── src
│   telemetry_generator.py
│   churn_model.py
│   difficulty_monitor.py
│
├── dashboard
│   app.py
│
├── plots
│   difficulty_curve.png
│   retention_curve.png
│   churn_probability.png
│   transition_heatmap.png
│   game_health_dashboard.png
│   level_health_chart.png
│
├── report
│   game_analytics_full_report.pdf
│   game_analytics_case_study_level50.pdf
│
├── requirements.txt
│
└── README.md
```

---

# Tools

Python libraries used:

- pandas
- NumPy
- matplotlib
- seaborn
- scikit-learn
- SciPy
- Streamlit

---

# Author

Aditya Bawane  

Game Analytics Portfolio

```
github.com/yourusername/game-analytics-project
```
