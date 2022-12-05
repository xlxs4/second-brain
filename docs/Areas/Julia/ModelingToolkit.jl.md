[Home · ModelingToolkit.jl](https://docs.sciml.ai/ModelingToolkit/dev/)

ModelingToolkit.jl is a modeling language. It can do both symbolic and numeric computation. It is highly performant and parallel. It is extendable because it brings ideas from symbolic CAS and causal/acausal equation-based modeling frameworks. The model can be input as a high-level description. Then, the model is analyzed and enhanced through symbolic preprocessing. It allows for automatic transformations, such as index reduction, to be applied before solving in order to easily handle equations that could not have been solved without symbolic intervention.

It mixes symbolic computing packages like [SymPy](https://www.sympy.org/en/index.html) or [Mathematica](https://www.wolfram.com/mathematica/) with equation-based modeling systems like the causal [Simulink](https://www.mathworks.com/products/simulink.html) and the acausal [Modelica](https://modelica.org/modelicalanguage.html). It can easily transform to and from different kinds of equations like DAEs into optimization problems and vice-versa. Before producing code, it simplifies and parallelizes the model.


