
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
- The ability to use the entire Symbolics.jl Computer Algebra System (CAS) as part of the modeling process.
- Import models from common formats like SBML, CellML, BioNetGen, and more.
- Extendability: the whole system is written in pure Julia, so adding new functions, simplification rules, and model transformations has no barrier.

[Home · ModelingToolkit.jl](https://docs.sciml.ai/ModelingToolkit/dev/#Feature-List)
