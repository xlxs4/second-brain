
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

## Equation Types

- [Ordinary differential equations](https://www.wikiwand.com/en/Ordinary_differential_equation)
- [Stochastic differential equations](https://www.wikiwand.com/en/Stochastic_differential_equation)
- [Partial differential equations](https://www.wikiwand.com/en/Partial_differential_equation)
- [Nonlinear systems](https://www.wikiwand.com/en/Nonlinear_system)
- [Optimization problems](https://www.wikiwand.com/en/Optimization_problem)
- [Continuous-Time Markov Chains](https://www.wikiwand.com/en/Continuous-time_Markov_chain)
- [Chemical Reactions](https://www.wikiwand.com/en/Chemical_reaction_network_theory) (via [Catalyst.jl](https://docs.sciml.ai/Catalyst/stable/))
- [Nonlinear Optimal Control](https://www.wikiwand.com/en/Optimal_control)

## Standard Library

See [[ModelingToolkitStandardLibrary.jl]]

## Model Import Formats

### CellML

[CellMLToolkit.jl](https://docs.sciml.ai/CellMLToolkit/stable/) can be used to import CellML models into ModelingToolkit. CellML is an XML-based open standard for mathematical models. It has a repository of more than a thousand models. While it's domain-agnostic, there's a focus on biomedical models. Currently, *some* of its active categories include:

- Cell Cycle
- Cell Migration
- Circadian Rhythms
- Gene Regulation
- Immunology
- Ion Transport
- Mechanical Constitutive Laws
- Metabolism
- Neurobiology
- PK/PD (pharmacokinetic/pharmacodynamic)
- Protein Modules
- Signal Transduction
- **Synthetic Biology**

CellMLToolkit.jl imports a CellML model in XML and outputs a ModelingToolkit.jl IR (Intermediate Representation) to work with using the general SciML ecosystem. 

### SBML

[SBMLToolkit.jl](https://docs.sciml.ai/SBMLToolkit/stable/) can be used to import SBML (Systems Biology Markup Language) models into ModelingToolkit and the general SciML ecosystem. It uses [SBML.jl](https://github.com/LCSB-BioCore/SBML.jl) which in turn provides a Julia wrapper to [libSBML](https://sbml.org/software/libsbml/).

### BioNetGen

You can use SBMLToolkit — more specifically, the `writeSBML()` export function.

BioNetGen is for biochemical reaction networks modeling. Thus, you can use [ReactionNetworkImporters.jl](https://docs.sciml.ai/ReactionNetworkImporters/stable/). You can also use ReactionNetworkImporters.jl to import:

- networks represented by dense or sparse substrate and product stoichiometric matrices
- networks represented by dense or sparse complex stoichiometric and incidence matrices

Notice that you can still use SBMLToolkit.jl, since you can export a model in SBML through BioNetGen (and [COPASI](https://copasi.org/), and [Virtual Cell](https://vcell.org/), etc.).

### Extension Libraries

There's a lot of libraries that add features to the general equation-based modeling ecosystem that has ModelingToolkit as its core. Some are:

- [Catalyst.jl](https://docs.sciml.ai/Catalyst/stable/): Symbolic representations of chemical reactions
- [DataDrivenDiffEq.jl](https://docs.sciml.ai/DataDrivenDiffEq/stable/): Automatic identification of equations from data
- [MomentClosure.jl](https://docs.sciml.ai/MomentClosure/dev/): Automatic transformation of `ReactionSystems` into deterministic systems
- [ReactionMechanismSimulator.jl](https://docs.sciml.ai/ReactionMechanismSimulator/stable): Simulating and analyzing large chemical reaction mechanisms
- [NumCME.jl](https://github.com/voduchuy/NumCME.jl): High-performance simulation of [chemical master equations](https://www.wikiwand.com/en/Master_equation) (CME)
- [FiniteStateProjection.jl](https://github.com/kaandocal/FiniteStateProjection.jl): High-performance simulation of CMEs via finite state projections
