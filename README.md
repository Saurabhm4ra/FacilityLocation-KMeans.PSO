# FacilityLocation-KMeans.PSO
This project focuses on solving the k median facility location problem with the use of constrained K-Means and PSO

# Introduction
Facility location problems are crucial in various sectors, including logistics, supply chain
management, and urban planning. The K-Median problem, a specific type of facility location
problem, aims to minimize the total distance between facilities and a set of demand points
while ensuring that each demand point is served by its nearest facility. This report details the
formulation, implementation, and optimization of a K-Median Facility Location Problem using
Mixed-Integer Linear Programming (MILP) and Particle Swarm Optimization (PSO).
## 1. Formulation of K-Median Problem as MILP
The traditional K-Median problem can be formulated as a MILP by incorporating additional
constraints to address specific requirements. In this variation, we extended the K-Median
model by introducing a minimum demand location constraint. This ensures that each facility
must meet a certain threshold of demand to be considered viable.
The MILP formulation includes:

● Decision Variables: Binary variables representing whether a facility is opened and
whether a demand point is assigned to a particular facility.
● Objective Function: Minimize the total distance between facilities and demand
points, weighted by the demand at each point.

● Constraints:
○ Each demand point is assigned to exactly one facility.
○ A facility can only serve demand points if it is opened.
○ Minimum demand constraint ensures that a facility must serve a certain
minimum demand to be considered as an active facility.
## 2. Implementation Using CBC Solver or gurobipy
To solve the MILP problem, we utilized the CBC (Coin-or branch and cut) solver, an
open-source solver suitable for MILP problems. The implementation involved:

● Model Construction: Building the MILP model with the specified constraints and
objective function.

● Solver Configuration: Setting up CBC to handle the optimization process.

● Solution Extraction: Running the solver to find the optimal facility locations and
assignments that minimize the objective function while satisfying all constraints.
The CBC solver effectively handled the complexity of the MILP model, providing an optimal
solution for the K-Median problem with the minimum demand constraint.

## 3. Reformulation and Optimization with PSO
To further enhance the model, we introduced a forbidden location constraint, which prevents
certain locations from being used as facilities due to logistical or operational reasons. This
addition required reformulating the MILP model to include:

● Forbidden Locations Constraint: A constraint that explicitly prohibits the selection
of specific locations as facilities.
To solve this reformulated model, we applied the Particle Swarm Optimization (PSO)
algorithm, which is a metaheuristic optimization technique inspired by the social behavior of
birds flocking or fish schooling. The steps involved:

● Initialization: Setting up a population of candidate solutions (particles) and initializing
their positions and velocities.

● Evaluation: Assessing the fitness of each particle based on the objective function
and constraints.

● Update Mechanism: Adjusting the positions and velocities of particles based on their
own best-known positions and the best-known positions of the swarm.

● Termination: Iterating until convergence criteria are met or a maximum number of
iterations is reached.

The PSO algorithm efficiently explored the solution space, accommodating the forbidden
locations constraint and providing a near-optimal solution to the K-Median problem.

## Conclusion

The optimization of the K-Median Facility Location Problem through MILP and PSO has
demonstrated effective strategies for addressing complex constraints and requirements. The
MILP formulation with minimum demand location constraints, solved using the CBC solver,
provided a robust solution for facility placement and demand assignment. The subsequent
reformulation incorporating forbidden location constraints and the application of PSO further
enhanced the optimization process. This approach ensures that the facility location decisions
are both feasible and optimal, balancing operational constraints and performance objectives.

## Future Work
Future research could explore hybrid approaches combining MILP and metaheuristic
algorithms, as well as extend the model to handle dynamic or multi-objective scenarios.
Further experimentation with different solvers and optimization techniques may also yield
additional insights into solving large-scale and complex facility location problems.
