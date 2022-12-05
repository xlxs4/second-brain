
## Description

ModelingToolkit.jl is a modeling language. It can do both symbolic and numeric computation. It is highly performant and parallel. It is extendable because it brings ideas from symbolic CAS and causal/acausal equation-based modeling frameworks. The model can be input as a high-level description. Then, the model is analyzed and enhanced through symbolic preprocessing. It allows for automatic transformations, such as index reduction, to be applied before solving in order to easily handle equations that could not have been solved without symbolic intervention.

It mixes symbolic computing packages like [SymPy](https://www.sympy.org/en/index.html) or [Mathematica](https://www.wolfram.com/mathematica/) with equation-based modeling systems like the causal [Simulink](https://www.mathworks.com/products/simulink.html) and the acausal [Modelica](https://modelica.org/modelicalanguage.html). It can easily transform to and from different kinds of equations like DAEs into optimization problems and vice-versa. Before producing code, it simplifies and parallelizes the model.

[Home · ModelingToolkit.jl](https://docs.sciml.ai/ModelingToolkit/dev/)

## Features

- Causal and acausal modeling ([Simulink](https://www.mathworks.com/products/simulink.html)/[Modelica](https://modelica.org/modelicalanguage.html)) 
- Automated model transformation, simplification, and composition
- Automatic conversion of numerical models into symbolic models
- Composition of models through the components, a lazy connection system, and tools for expanding/flattening
- Pervasive parallelism in symbolic computations and generated functions
- Transformations like alias elimination and tearing of nonlinear systems for efficiently numerically handling large-scale systems of equations
- The ability to use the entire [Symbolics.jl](https://github.com/JuliaSymbolics/Symbolics.jl) CAS as part of the modeling process.
- Import models from common formats like [SBML](https://sbml.org/), [CellML](https://www.cellml.org/), [BioNetGen](https://bionetgen.org/), and more.
- Extendability: the whole system is written in pure [Julia](https://julialang.org/), so adding new functions, simplification rules, and model transformations has no barrier.

[Feature List · ModelingToolkit.jl](https://docs.sciml.ai/ModelingToolkit/dev/#Feature-List)

### Equation Types

- [Ordinary differential equations](https://www.wikiwand.com/en/Ordinary_differential_equation)
- [Stochastic differential equations](https://www.wikiwand.com/en/Stochastic_differential_equation)
- [Partial differential equations](https://www.wikiwand.com/en/Partial_differential_equation)
- [Nonlinear systems](https://www.wikiwand.com/en/Nonlinear_system)
- [Optimization problems](https://www.wikiwand.com/en/Optimization_problem)
- [Continuous-Time Markov Chains](https://www.wikiwand.com/en/Continuous-time_Markov_chain)
- [Chemical Reactions](https://www.wikiwand.com/en/Chemical_reaction_network_theory) (via [Catalyst.jl](https://docs.sciml.ai/Catalyst/stable/))
- [Nonlinear Optimal Control](https://www.wikiwand.com/en/Optimal_control)
