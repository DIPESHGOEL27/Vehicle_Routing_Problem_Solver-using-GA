# Vehicle Routing Problem Solver with Genetic Algorithms

![VRP Solver](https://github.com/DIPESHGOEL27/Vehicle_Routing_Problem_Solver-using-GA/raw/main/vrp_sample_output.png)

## Overview

This repository contains an implementation of a vehicle routing problem (VRP) solver using genetic algorithms (GAs). The VRP is a combinatorial optimization problem where a fleet of vehicles must visit a set of locations to deliver goods, minimizing total distance traveled and balancing workload among vehicles.

The VRP solver employs a multi-objective genetic algorithm to find near-optimal solutions for complex routing scenarios. It balances the trade-off between minimizing total distance traveled by vehicles and minimizing the imbalance among vehicles' travel distances.

## Features

- **Genetic Algorithm Framework**: Utilizes the DEAP library to implement a flexible and customizable genetic algorithm framework.
- **Multi-Objective Optimization**: Considers multiple objectives simultaneously, including total distance traveled and balance among vehicles.
- **Visualization**: Provides visualizations of optimized routes using Matplotlib, aiding in understanding and analysis of solutions.
- **Scalability**: Handles large-scale VRP instances with varying numbers of locations and vehicles efficiently.
- **Customizable Parameters**: Allows customization of genetic algorithm parameters such as population size, crossover rate, mutation rate, and selection mechanism.
- **Reproducibility**: Seeds the random number generator for reproducibility of results.

## Genetic Algorithm Working

### Selection Method
The implemented GA uses tournament selection for parent selection. In tournament selection, individuals are randomly selected in groups (tournaments), and the fittest individual from each tournament is chosen as a parent for reproduction. This method ensures that individuals with higher fitness have a higher probability of being selected as parents while allowing for diversity in the selected individuals.

### Crossover Method
The GA employs Partially Matched Crossover (PMX) for crossover operation. PMX is suitable for permutation-based representations, such as the routing problem, where the order of locations matters. It creates offspring by partially matching segments of two parent chromosomes and exchanging the remaining elements to ensure offspring are valid permutations of locations.

### Mutation Method
The mutation operator used is Shuffle Indexes Mutation. This mutation method shuffles a subset of indices (locations) in an individual's chromosome with a low probability. It introduces random changes to the order of locations, promoting exploration of the search space while maintaining the validity of solutions.

### Fitness Evaluation Function

The fitness evaluation function (`evalVRP`) computes the fitness of an individual solution in the genetic algorithm based on two objectives:

1. **Total Distance**: Minimizes the total distance traveled by all vehicles in their respective routes. This is achieved by summing up the distances between consecutive locations for each vehicle.

2. **Balance Penalty**: Penalizes solutions with imbalanced workload among vehicles. The balance penalty is calculated as the standard deviation of distances traveled by each vehicle, encouraging a more equitable distribution of workload.

#### Design Considerations:

- **Objective Scaling**: The function scales the balance penalty using standard deviation to provide a meaningful measure of imbalance regardless of problem scale.

- **Multi-Objective Optimization**: By considering multiple objectives simultaneously, the function guides the search towards solutions that are both efficient and balanced.

- **Depot Handling**: Each vehicle's route starts and ends at the depot, ensuring feasibility and that all locations are visited exactly once.

## Getting Started

### Prerequisites

- Python 3.x
- DEAP library (`pip install deap`)
- Matplotlib library (`pip install matplotlib`)

### Installation

1. Clone the repository:

```bash
git clone https://github.com/DIPESHGOEL27/Vehicle_Routing_Problem_Solver-using-GA.git
cd Vehicle_Routing_Problem_Solver-using-GA
```

2. Install dependencies:

```bash
pip install -r requirements.txt
```

### Usage

Run the main script to execute the genetic algorithm solver:

```bash
python main.py
```

Follow the instructions to set up parameters and visualize the optimized routes.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, please open an issue or submit a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
