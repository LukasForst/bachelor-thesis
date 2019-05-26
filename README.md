# Design and implementation of a scalable server for parallelization of optimization algorithms execution
Bachelor's thesis - FEE CTU

## Abstract
Large-scale optimization problems are non-trivial to solve 
and require a significant amount of computational resources as well as computational time to find a solution.
The challenge is to solve not only a single task but a multitude of them in a parallel manner.
Additionally, the tasks are non-homogeneous, 
often describing a different problem. 
This problem can be solved by designing 
and intelligent scheduler able to schedule such tasks on a distributed computational platform.


This work introduced the load balancer developed explicitly for the optimization algorithms,
which should minimize resources wasting 
and increase the performance using correct utilization distribution across the multiple instances of such algorithms.
The thesis analyzes the state-of-the-art solutions and technologies,
that are being used to solve load balancing problems in the large infrastructures.
Subsequently, the new domain-specific load balancing solution is proposed.
The thesis proposes the mathematical formalization of the load balancing optimization problem
and the related challenge, such as hyperbola time series prediction.
Subsequently, the thesis designs the microservices architecture for the load balancer 
and also delivers the complete implementation of the proposed system.
This thesis also proposed and implemented the simulations and experiments, 
which evaluates the implemented load balancer.


The final chapter of the thesis addresses out of scope steps for complete productionalization of the proposed load balancing system
and also outlines the future development of the tools and libraries,
that was developed alongside the primary system.

## Keywords
load balancing, optimization algorithms, combinatorial optimization, TASP, OptaPlanner Kotlin, Ktor, Docker