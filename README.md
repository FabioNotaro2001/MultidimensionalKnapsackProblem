# Multidimensional Knapsack Problem Solver 🧠

This repository contains a Python implementation of a solver for the **0‑1 Multidimensional Knapsack Problem** (MDKP), developed as part of an *Operative Research* (Ricerca Operativa) course project. It includes both a Jupyter notebook for interactive exploration and a standalone script for command‑line usage.

## 📁 Repository Structure


.
├── LICENSE
├── Ricerca_operativa.ipynb # Jupyter notebook with analysis, data exploration, testing
└── ricerca_operativa.py # Command‑line Python solver script

## ⚙️ Requirements

- Python 3.7 or above  
- Uses only standard library modules (no external dependencies)  
- The script reads input from a CSV or TXT file in plain text format (one instance per line).

## 🧩 Problem Description

The **Multidimensional Knapsack Problem (MDKP)** is defined as follows:

- You have *n* items; each item *j* has a **value** \(v_j\).
- There are *m* resource constraints; each item j consumes \(w_{i,j}\) units of resource *i*.
- Each resource *i* has capacity \(C_i\).
- The goal is to select a subset of items \(S \subseteq \{1…n\}\) to **maximize total value**
  
  \[
    \max \sum_{j \in S} v_j
  \]
  
  **subject to**
  
  \[
    \sum_{j \in S} w_{i,j} \le C_i, \quad \forall i = 1..m
  \]
  
- This solver handles the **0‑1** variant (each item is either taken or not).

The notebook `Ricerca_operativa.ipynb` contains the mathematical formulation, examples, result tables and performance charts.

## 🚀 Usage

1. **Clone the repository**  
   ```bash
   git clone https://github.com/FabioNotaro2001/MultidimensionalKnapsackProblem.git
   cd MultidimensionalKnapsackProblem

Prepare an instance file, e.g. instance1.txt, formatted like:
# Optional: header or comment lines starting with ‘#’
value_1 weight1_1 weight2_1 ... [weight_m_1]
value_2 weight1_2 weight2_2 ...
…
capacity_1 capacity_2 … capacity_m

Run the solver script using:
python3 ricerca_operativa.py instance1.txt
    Output will include:

        Selected item indices

        Total value

        Remaining capacities for each resource

The script also prints runtime and may optionally produce basic performance diagnostics.
🧠 Algorithm Description

The implementation currently uses a heuristic / dynamic programming approach (Python‑only, without commercial solvers).
It incorporates:

    A greedy initialization phase based on value‑to‑weight ratio

    An optional local search to improve the solution

    A runtime bound (configurable from within ricerca_operativa.py)

Check the notebook for comparisons of runtime and solution quality on standard test instances.
📊 Exploring with the Notebook

Open Ricerca_operativa.ipynb in Jupyter to:

    View the mathematical model and constraints

    Run experiments on synthetic or real datasets

    Visualize solution quality vs. time

    Study sensitivity to number of dimensions or item count

You can modify the notebook or script to plug in alternative solution strategies, such as ILP with pulp, metaheuristics, or Python‘s mip package.
🧪 Adding Your Own Algorithms

To extend the solver:

    Implement your function in ricerca_operativa.py, following the interface:
    def solve_mdkp(values: List[float], weights: List[List[int]], capacities: List[int]) -> List[int]:
    ...

    Add your code to the notebook to benchmark it.

    Keep the format consistent if using additional modules.

👨‍💼 Attribution

This project was originally developed for an academic exercise in Ricerca Operativa course, demonstrating practical implementation and analysis of combinatorial optimization.
📄 License

This project is released under the MIT License. See the LICENSE file for details.

Feel free to customize or extend the solver and analysis to suit your research or course requirements.

Repository snapshot: contains a Python solver script and a companion notebook for interactive analysis. 

---

### ✅ How to commit this README

1. Copy the above markdown content.
2. Paste it into a file named `README.md` at the root of your GitHub repo.
3. Commit and push:

```bash
git add README.md
git commit -m "Add project README"
git push
