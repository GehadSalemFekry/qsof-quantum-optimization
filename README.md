# Bin Packing Optimization Project

## Overview
This project provides an in-depth analysis of various optimization methods to solve the **bin packing problem**, a classic combinatorial optimization problem where items of different weights are packed into bins of fixed capacity, minimizing the number of bins used. The project explores different optimization techniques, including **Integer Linear Programming (ILP)**, **Brute Force**, **D-Wave Quantum Annealing**, **Variational Quantum Eigensolver (VQE)**, and **Quantum Approximate Optimization Algorithm (QAOA)**.

## Optimization Methods

### 1. Integer Linear Programming (ILP)
ILP formulates the bin packing problem as a linear programming model using binary decision variables to determine whether an item is placed in a bin and whether a bin is used. Gurobi is used to solve the ILP and obtain an optimal solution.

### 2. Brute Force Approach
The brute force approach explores all possible combinations of placing items into bins. This guarantees finding the optimal solution but is highly inefficient for larger instances due to its exponential time complexity.

### 3. D-Wave Quantum Annealing
The D-Wave quantum annealer is used to solve a QUBO (Quadratic Unconstrained Binary Optimization) representation of the problem. Quantum annealing provides an efficient way to solve combinatorial optimization problems, especially for larger instances where classical methods struggle.

### 4. Variational Quantum Eigensolver (VQE)
VQE uses parameterized quantum circuits and classical optimization to find the minimum eigenvalue of an Ising Hamiltonian, which represents the bin packing problem. This hybrid quantum-classical approach is suitable for near-term quantum computers.

### 5. Quantum Approximate Optimization Algorithm (QAOA)
QAOA is another hybrid quantum-classical approach that alternates between applying problem and mixer unitaries to approximate the solution to the bin packing problem. It is well-suited for combinatorial problems, but it may require tuning of depth (`p`) and parameters to achieve good results.

## Results Analysis

### Small Problem Instance
- **Item Weights**: `[1, 1, 2]`
- **Bin Capacity**: `2`

**ILP Solution**: The optimal solution used 2 bins, with items `[1, 1]` in Bin 0 and item `[2]` in Bin 1.

**Brute Force and D-Wave Solutions**: Both found the same optimal solution as ILP, confirming correctness.

**VQE and QAOA Solutions**: These methods provided suboptimal results compared to ILP. VQE struggled with parameter optimization, while QAOA faced limitations with circuit depth.

### Large Problem Instance
- **Brute Force**: Took an excessive amount of time, making it impractical for large instances.
- **VQE and QAOA**: Encountered memory errors due to resource limitations and circuit complexity.
- **D-Wave Quantum Annealing**: Successfully solved the problem efficiently, emerging as the most viable solution for larger instances in terms of both optimality and efficiency.

## Key Takeaways
- **ILP** and **Brute Force** are reliable but do not scale well for larger problem instances.
- **D-Wave** quantum annealing provided an efficient and scalable solution for large problem instances.
- **VQE** and **QAOA** require further hardware advancements or more efficient ansatz designs to handle larger problems effectively.

## Setting Up the Environment
To run this project, you need to set up a Python environment with all necessary dependencies. You can do this by following the steps below.

### Creating and Activating a Virtual Environment
First, create and activate a virtual environment:

- On Windows:
  ```sh
  python -m venv env
  path\to\your\env\Scripts\activate
  ```

- On macOS/Linux:
  ```sh
  python3 -m venv env
  source path/to/your/env/bin/activate
  ```

### Installing Dependencies
After activating the virtual environment, install the dependencies listed in the `requirements.txt` file:

```sh
pip install -r requirements.txt
```


This command will create a `requirements.txt` file that lists all the installed packages and their versions.

## Running the Notebook
To explore the optimization methods and see the analysis for both small and large problem instances, run the Jupyter notebook provided in this project.

## Conclusion
This project provides a comparative study of different optimization methods for the bin packing problem. The results show that while classical methods like **ILP** and **Brute Force** work well for small instances, **D-Wave Quantum Annealing** is the best choice for larger instances due to its scalability and efficiency. **VQE** and **QAOA** are promising but require advancements in quantum hardware or more efficient techniques to handle larger problems effectively.

## Future Work
- **Improving Quantum Circuit-Based Approaches**: Explore more efficient ansatz designs for VQE and QAOA to reduce memory requirements and improve solution quality.
- **Hybrid Quantum-Classical Techniques**: Develop hybrid approaches that combine classical preprocessing with quantum optimization to handle larger problems more effectively.
- **Use of Real Quantum Hardware**: Test the quantum algorithms on real quantum hardware to further evaluate their practical feasibility and performance.


## Acknowledgments
Special thanks to the developers of Gurobi, D-Wave, and Qiskit for their tools, which were instrumental in the exploration and implementation of the optimization techniques in this project. 

Also specially thanks for the QSOF committee for allowing me to go through this research journey, I enjoyed working on this assessment a lot. 

