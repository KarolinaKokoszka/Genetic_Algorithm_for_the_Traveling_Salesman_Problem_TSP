# 🧬 Genetic_Algorithm_for_the_Traveling_Salesman_Problem_TSP
This project implements a genetic algorithm to solve the TSP — finding the shortest possible route that visits each city exactly once and returns to the starting point. It includes customizable selection, crossover, and mutation strategies, with visualizations of route evolution and optimization progress over generations.

## 📌 Algorithm Overview

The genetic algorithm simulates natural evolutionary processes, including:
- **Selection** of the best routes (individuals),
- **Crossover** (recombination) of parent routes,
- **Mutation** (e.g., inverting a segment of the route),
- **Elitism**, i.e., preserving the best solutions unchanged.

### Execution Steps:
1. **Initialization** – generate an initial population of random routes.
2. **Evaluation** – compute the total length of each route.
3. **Selection** – choose parent routes for reproduction (`ranking_list` or `grouped_roulette` methods).
4. **Crossover** – order-based crossover (OX) between selected parents.
5. **Mutation** – random inversion of route segments with a certain probability.
6. **Elitism** – carry over the best routes unchanged to the next generation.
7. **Evolution** – repeat the above steps over several generations.

## ⚙️ Parameters

- `num_cities` – number of cities (e.g., 30)
- `pop_size` – population size (e.g., 100)
- `num_generations` – number of generations (e.g., 300)
- `crossover_prob` – crossover probability (e.g., 0.9)
- `mutation_prob` – mutation probability (e.g., 0.05–0.15)
- `elite_size` – number of elite individuals preserved without changes
- `method` – selection method: `ranking_list` or `grouped_roulette`
- `use_circle` – whether cities should be arranged in a circle (True/False)
- `a`, `b` – parameters for the grouped roulette selection method

## 📊 Results and Observations

- The algorithm **effectively optimizes the route** over time, as shown by the decreasing best distance across generations.
- The `ranking_list` method offers **greater stability** and **faster convergence** to optimal routes.
- The `grouped_roulette` method can also perform well but typically requires more precise parameter tuning.
- For a higher number of cities, increasing `mutation_prob` can help avoid premature convergence.

## 📷 Visualizations

The notebook generates:
- route plots for selected generations,
- optimization progress plots (`best`, `average`, and `worst` distances).

## ▶️ Example Usage

```python
run_genetic_algorithm(
    num_cities=30,
    crossover_prob=0.94,
    mutation_prob=0.09,
    method='ranking_list',
    use_circle=True
)
