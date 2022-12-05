[Model Calibration and Parameter Estimation with JuliaSim Model Optimizer - YouTube](https://www.youtube.com/watch?v=TkmpICaFDrM&list=PLC0QOsNQS8hZ3JXKzx32BidNxyIdYoPeY&index=21)

JuliaSim: a modern SciML suite

![[model-optimizer1.png]]

![[model-optimizer2.png]]

![[model-optimizer3.png]]

robust
parallel
unidentifiable model parameters -> virtual populations: sets of parameters which sufficiently fit all trials, all observations. A trial is a different variation of the model which can be ran, an experiment. We can have multiple trials.

![[model-optimizer4.png]]

## Model paradigms

### Causal Modeling

Describe the causal mechanisms of the system; clear rules for the interactions between functional blocks. An analogy to imperative programming, we're interested with the flow of computation. It leads us nicely to

### Acausal modeling

Describe the behavior and the properties of the model components and the models are built up out of the composition of the components. The overall dynamics of the model fall out of the cumulative behavior of the composition ->  declarative programming, we only worry about the relationships and the connections between the components, and the individual components, and not the flow of computation

![[model-optimizer5.png]]

![[model-optimizer6.png]]

![[model-optimizer7.png]]

![[model-optimizer8.png]]

easy to construct
classic real world example of what a chaotic system can look like

at least one nonlinear element ? check wikiwand

![[model-optimizer9.png|700]]

![[model-optimizer10.png|700]]

1. define model parameters not readily available in the model library
2. create the model components (using the model components and the nonlinear resistor we built)

![[model-optimizer11.png]]

3. Define the relationships between the components

![[model-optimizer12.png]]

typically here: read the real world data from csv or something, and then.... but here we're using the `sol` from above to create the data

![[model-optimizer13.png]]

![[model-optimizer14.png]]

![[model-optimizer15.png]]

![[model-optimizer16.png]]

![[model-optimizer17.png]]

![[model-optimizer18.png]]

![[model-optimizer19.png]]

![[model-optimizer20.png]]

![[model-optimizer21.png]]

![[model-optimizer22.png]]

![[model-optimizer23.png]]

![[model-optimizer24.png]]

![[model-optimizer25.png]]
