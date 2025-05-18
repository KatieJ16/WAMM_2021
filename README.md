# 🧪 SIR Model Simulation — COVID-19 Spread Dynamics

## 📌 Overview

This project simulates the spread of an infectious disease using a probabilistic and a deterministic version of the classic **SIR (Susceptible-Infected-Recovered)** model. It was inspired by the paper *"A SIR model assumption for the spread of COVID-19 in different communities"* and built during a mentorship exploring probability and statistics.

## 🎯 Objectives

* Understand the mathematical underpinnings of the SIR model
* Create a simplified version of the model using probabilistic simulation
* Compare it to the standard SIR differential equation model using SciPy
* Experiment with how parameters like interaction rate and infectious period affect outcomes

---

## 📚 Background: What Is the SIR Model?

The SIR model divides the population into three compartments:

* `S` - Susceptible individuals
* `I` - Infected individuals
* `R` - Recovered (and immune) individuals

**Basic equations** used in the classical deterministic model:

```math
dS/dt = -βSI/N
dI/dt = βSI/N - γI
dR/dt = γI
```

Where:

* `β` = infection rate (based on interactions and probability)
* `γ` = recovery rate (1 / days\_infectious)
* `N` = total population

---

## 🛠 Features of This Simulation

### ✅ Probabilistic Model (Discrete Simulation)

* Each infected person interacts with `people_interact` people per day
* Each interaction has `infect_chance` probability of infection
* Infected individuals move to recovered after `days_infectious` days
* Tracks population daily for 14 days

### ✅ Ideal SIR Model (ODE Simulation)

* Uses `scipy.integrate.odeint` to solve the SIR equations numerically
* Based on the same initial conditions and parameters for fair comparison

---

## 📈 Parameters Used

| Parameter         | Value         |
| ----------------- | ------------- |
| Total population  | 1,000,000     |
| Initial infected  | 1             |
| Interaction count | 10 people/day |
| Infection chance  | 0.5           |
| Infectious period | 3 days        |

---

## 📊 Graphs and Comparison

The project outputs:

* A graph of **S, I, R** over 14 days from both simulation methods
* A plot comparing infected counts in both models
* Visualization of daily new infections and recoveries

Example output:

![Comparison Graph](results/comparison_plots.png)

---

## 🚀 Getting Started

### 📦 Install Dependencies

```bash
pip install numpy matplotlib scipy
```

### ▶️ Run the Simulation

```bash
python main.py
```

---

## 🧪 Experimentation Ideas

The model can be tweaked to simulate different real-world conditions:

* **Social distancing**: reduce `people_interact`
* **Mask-wearing or improved hygiene**: reduce `infect_chance`
* **Longer illness duration**: increase `days_infectious`
* **Superspreaders or events**: increase initial infected or burst interactions

---

## 🧠 Future Improvements

* Add **policy simulation** (lockdowns, holidays, vaccination)
* Visualize outcomes for **different countries or states**
* Add sliders/GUI for interactive parameter tweaking
* Extend to SEIR or stochastic SIR variations

---

## 👩‍🏫 Acknowledgments

Special thanks to my mentor **Katie** for her guidance and for helping explore this intersection of code and epidemiology!

---
