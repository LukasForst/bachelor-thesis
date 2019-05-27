# Design and implementation of a scalable server for parallelization of optimization algorithms execution
Bachelor's thesis - FEE CTU.

Text of the submited thesis can be found in the git submodule `text` and the implemented load balancer in the module `implementation`.
The final thesis PDF file is also located in the root of this git `thesis.pdf`.

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

## Introduction
The globalization of the world’s economies is a major challenge to local industry 
and it is pushing the manufacturing sector to the transformation called *Industry 4.0*.
In order to become more competitive, 
manufacturers need to embrace emerging technologies, 
such as advanced analytics, artificial intelligence 
and mathematical optimization to improve their efficiency and productivity.

Specifically the manufacturing industry sector,
which have high production costs,
faces multiple problems,
where employing mathematical optimization can reduce cost or improve the efficiency of the process.
Taking as an example the car manufacturers,
there are many processes,
that can be optimized to reduce their cost or to use needed resources more efficiently,
such as internal logistics, car parts transportation, parts stocking, cars manufacturing 
and the allocation of the various types of resources.
These optimization challenges are often solved by the proprietary software systems with included optimization engine,
where the one problem domain is usually handled by the single program operating specifically with such domain.

These applications typically have a user interface for the data visualization
and an engine running an optimization algorithm.
Although the data visualization part of the application does not require powerful hardware,
the immense complexity of the mathematical optimization problems 
and thus the performance requirements for such optimization engine solving them, are not always satisfiable.
Moreover,
the computer performance is a finite resource
and it costs money paid for the computer components or for the electricity used.
For those reasons,
the optimization software systems have often limited access to computer resources.
In addition,
this computer performance is not used all the time,
since the typical usage of such application lays mainly in data visualization,
hence the performance, required only when the optimization engine is running, is unused.

Using such software architecture seems to be highly inefficient,
since the instances, that are in time **t** running the optimization algorithm, are overwhelmed 
and at the same time **t**,
the applications, that are not running the optimization tasks,
do not use their powerful computer resources at all.

The potential solution for these problems lays in microservices architecture,
where the parts of the applications are independent and able to run separately.
Using this approach enables distributed computing
and therefore outsourcing the demanding optimization engine to more powerful servers.
This approach solves the lack of resources for the optimization engine on the less powerful servers,
but it also introduces a new challenge in the load balancing of the servers,
where the optimization engine is being executed.

In this thesis, we would like to present the load balancer specifically developed for the optimization algorithms,
which should minimize resources wasting 
and increase the performance using correct utilization distribution across the multiple instances of such algorithms.
In the first chapters,
the thesis analyzes the state-of-the-art solutions and technologies,
that are being used to solve load balancing problems in the large infrastructures.
These technologies are evaluated 
and the new domain-specific load balancing solution is proposed.
The thesis then transforms and formalizes the load balancing optimization problem into an integer linear programming problem.
The related challenges arising from the problem formalization, such as hyperbola time series prediction, are defined 
and the solutions for such problems are proposed.
Subsequently, the thesis designs and evaluates the microservices architecture for the load balancer 
and also delivers the complete implementation of the load balancer.
This thesis also proposed and implemented the simulations and experiments, 
which evaluates the implemented load balancer.

In the last chapter,
the future work is addressed 
and the steps, for moving the load balancer into the production environment, are proposed.
Apart from the planned steps for the load balancer system,
the last chapter outlines the future of the developed tools and libraries.