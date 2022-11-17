
JuliaSim: a modern SciML suite

![[sim1.png]]

![[sim2.png]]

![[sim3.png]]

robust
parallel
unidentifiable model parameters -> virtual populations: sets of parameters which sufficiently fit all trials, all observations. A trial is a different variation of the model which can be ran, an experiment. We can have multiple trials.

![[sim4.png]]

## Model paradigms

### Causal Modeling

Describe the causal mechanisms of the system; clear rules for the interactions between functional blocks. An analogy to imperative programming, we're interested with the flow of computation. It leads us nicely to

### Acausal modeling

Describe the behavior and the properties of the model components and the models are built up out of the composition of the components. The overall dynamics of the model fall out of the cumulative behavior of the composition ->  declarative programming, we only worry about the relationships and the connections between the components, and the individual components, and not the flow of computation

![[sim5.png]]

![[sim6.png]]

![[sim7.png]]

![[sim8.png]]

easy to construct
classic real world example of what a chaotic system can look like

at least one nonlinear element ? check wikiwand

![[sim9.png]]

![[sim10.png]]

1. define model parameters not readily available in the model library
2. create the model components (using the model components and the nonlinear resistor we built)

![[sim11.png]]

3. Define the relationships between the components

![[sim12.png]]

typically here: read the real world data from csv or something, and then.... but here we're using the `sol` from above to create the data

![[sim13.png]]

![[sim14.png]]

![[sim15.png]]

![[sim16.png]]

![[sim17.png]]

![[sim18.png]]

![[sim19.png]]

![[sim20.png]]

![[sim21.png]]

![[sim22.png]]

![[sim23.png]]

![[sim24.png]]

![[sim25.png]]
