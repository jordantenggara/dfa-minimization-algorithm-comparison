# DFA Minimization Algorithm Comparison

This repository contains a computational experiment for comparing three approaches in Deterministic Finite Automaton (DFA) minimization:

1. Moore Algorithm
2. Dynamic Programming through table-filling and memoization
3. Divide and Conquer strategy for equivalent state grouping

The project was created for the **Analisis dan Strategi Algoritma** course assignment.

## Project Title

**Perbandingan Algoritma Dynamic Programming, Divide and Conquer, dan Moore dalam Minimasi Deterministic Finite Automaton untuk Mengelompokkan State Ekuivalen**

## Author

**Jordan Tenggara**  
**[redacted]**  
Department of Informatics  
Universitas Diponegoro

## Overview

A Deterministic Finite Automaton (DFA) may contain different states that behave equivalently for every possible input string. These equivalent states can be grouped and minimized without changing the language accepted by the DFA.

This project compares Moore, Dynamic Programming, and Divide and Conquer based on:

- Number of states before minimization
- Number of states after minimization
- Equivalent state groups
- State reduction percentage
- Execution time
- Consistency of results compared to Moore

## Repository Structure

```text
dfa-minimization-algorithm-comparison/
│
├── README.md
├── requirements.txt
├── .gitignore
│
├── notebooks/
│   └── dfa_minimization_algorithm_comparison.ipynb
│
├── data/
│   └── dfa_dataset_final.json
│
├── results/
│   └── dfa_minimization_experiment_results.csv
│
└── report/
    └── Tubes_ASA_Jordan_Tenggara_24060124120044.pdf
```

## Dataset

The dataset is stored in JSON format. Each DFA contains:

- `name`
- `states`
- `alphabet`
- `start_state`
- `accept_states`
- `transitions`

The input is limited to DFA data that has already been represented in JSON format. This project does not include conversion from DFA diagrams, images, regular expressions, NFA, or ε-NFA.

## Algorithms

### Moore Algorithm

Moore is used as the main baseline algorithm. It minimizes DFA using partition refinement by separating final and non-final states, then repeatedly refining partitions based on transition behavior until stable groups are obtained.

### Dynamic Programming

Dynamic Programming is applied through a table-filling approach with memoization. Each pair of states is treated as a subproblem. The result of each state-pair comparison is stored so it can be reused during the equivalence checking process.

### Divide and Conquer

Divide and Conquer is used as an experimental strategy. The state set is divided into smaller subsets, processed recursively, and then combined again by checking equivalence across subsets.

## Experiment Results

The experiment uses 16 DFA samples. Each DFA is tested using the three algorithms.

Summary of average execution time:

| Algorithm | Average Execution Time |
|---|---:|
| Moore | 0.000114 s |
| Divide and Conquer | 0.000260 s |
| Dynamic Programming | 0.000497 s |

All three algorithms produced the same minimized state count for all tested DFA samples. The main difference between the algorithms appears in execution time and processing strategy.

## How to Run

1. Clone this repository.

```bash
git clone https://github.com/your-username/dfa-minimization-algorithm-comparison.git
cd dfa-minimization-algorithm-comparison
```

2. Install dependencies.

```bash
pip install -r requirements.txt
```

3. Open the notebook.

```bash
jupyter notebook notebooks/dfa_minimization_algorithm_comparison.ipynb
```

You can also open the notebook directly in Google Colab.

## Requirements

The main external libraries used are:

- pandas
- matplotlib

Other libraries used in the notebook, such as `json`, `time`, `dataclasses`, `typing`, `itertools`, and `collections`, are part of the Python standard library.

## Notes

The execution time results may vary depending on the runtime environment. The reported results are based on the same experimental environment and should be interpreted as relative comparisons between algorithms, not as absolute performance values for all possible DFA cases.

## License

This repository is created for academic purposes.
