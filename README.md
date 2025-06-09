
# NBA Schedule Optimization

This repository contains the code, results, and write-up for an integer programming project that optimizes the National Basketball Association (NBA) schedule. The main objectives are:

- **Minimize back-to-back games** to improve player health and performance
- **Reduce overall travel distance** to lower fatigue, expenses, and carbon emissions

The optimization is performed using **Google OR-Tools Constraint Programming** framework.

## 🚀 Features

- Models the NBA schedule without conferences or divisions
- Ensures each team plays **82 games** (41 home, 41 away)
- Prevents more than **1 game per team per day**
- Tracks team locations daily for accurate **travel distance** calculation
- Balances minimizing **back-to-back games** and **travel miles** with a tunable weight parameter `α`
- Produces an optimized, feasible 82-game schedule with significantly improved metrics

## 🧠 Optimization Goals

- **Back-to-Back Games:** Down from 14.9 (NBA average) to **0.8 per team**
- **Total Travel Distance:** Down from 42,435 miles to **37,609.9 miles per team**

## 📁 Repository Structure

- `NBA_Scheduling.ipynb`: Jupyter notebook containing all implementation code
- `final_solution.txt`: Final feasible 82-game schedule output (one file with each game day’s matchups)
- `OR2_FinalProject_GroupF.pdf`: Full academic paper detailing our methodology, motivation, and results

## 📊 Mathematical Formulation

Objective Function:
```
Minimize:
    ∑ BackToBackGames + (1/3000) * ∑ TravelDistance
```

Key Constraints:
- Each team plays exactly **82 games**
- Each team has **41 home and 41 away games**
- At most **one game per team per day**
- All teams face each other **2–3 times**
- Travel distance based on previous location, not always home

## 📦 Technologies Used

- Python 3.10
- Google OR-Tools (CP-SAT)
- geopy (for real-world stadium distances)
- Google Colab (to manage memory usage during solving)

## 📈 Results Summary

| Metric                        | NBA Avg | Initial Model | Final Model |
|------------------------------|---------|----------------|--------------|
| Back-to-Back Games / Team    | 14.9    | 6.97           | **0.8**      |
| Travel Distance / Team (mi)  | 42,435  | 68,710         | **37,609.9** |

## 🔧 How to Run

1. Install dependencies:  
```bash
pip install ortools geopy
```

2. Run `NBA_Scheduling.ipynb` in Jupyter or Google Colab.

3. Generated schedule will be saved to `solution1.txt`.

## 📄 Authors

- Animesh Ghose
- Adel Heddadji
- Ashwin Ramanathan
- Kwaku Bimpong

## 📚 Paper

See `OR2_FinalProject_GroupF.pdf` for full explanation, mathematical derivation, and results discussion.

---

Built as part of the **21-393 Operations Research** course at Carnegie Mellon University, Fall 2024.
