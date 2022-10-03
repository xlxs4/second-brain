## Proposed Abstract



## Description

#### Mathematics TL;DR: Model, optimization, etc. (technical stuff that he can immediately understand, abstracted from the actual application and everything bio)



#### Bio introduction (ELI5)



#### Actual bio introduction



#### Mathematics

We use a single mathematical framework to describe the relationship between the activator concentration and the production rate of either the reporter or autofeedback activator. We assume that the rate of production of either the reporter or autoactivator species, $(dX/dt)_{produce}$, can be described by the sum of a basal rate and a Hill function:

$$\begin{pmatrix}\frac{dX}{dt}\end{pmatrix}_{produce} = s + \frac{\beta A^n}{K^n + A^n} \tag{1}$$
where $s$ is the basal rate of production of activator, $n$ is the Hill cooperativity, $K$ is the concentration of activator that yields half the maximal production rate, $\beta$ is the maximal rate of protein production, and $A$ is the activator consumption ([[@alonIntroductionSystemsBiology2019]]).
The decay rate of either the reporter or autoactivator concentration is affected by both dilution due to cell growth and protein degradation. However, since the reporter protein and the autoactivator are degraded at a rate that is many time slower than their dilution rate, the decay in the species concentration can be simplified to
$$\begin{pmatrix}\frac{dX}{dt}\end{pmatrix}_{decay} = - \frac{ln2}{\tau}X \tag{2}$$
where $\tau$ is the time required for the number of cells to double by growth. The overall change in the concentration of the reporter or autofeedback activator can then be written as
$$\frac{dX}{dt} = s + \frac{\beta A^n}{K^n + A^n} - \frac{ln2}{\tau}X \tag{3}$$
At steady state, the production rate is balanced by the decay rate, so the relationship between the steady-state activator concentration, $A$, and steady-state reporter concentration, $R$, can be written as
$$R = \frac{ln2}{\tau}\begin{pmatrix}s + \frac{\beta A^n}{K^n + A^n}\end{pmatrix} \tag{4}$$
In the case of the positive feedback loop, we assume that the autofeedback gene is activated identically by the sensor-derived activator and the autofeedback activator, so we can rewrite Equation $3$ as
$$\frac{dA_A}{dt} = s + \frac{\beta(A_A + A_s)^n}{K^n + (A_A + A_s)^n} - \frac{ln2}{\tau}A_A \tag{5}$$
where $A_A$ is the autoactivator concentration and $A_s$ is the sensor-derived activator concentration.

#### Pair bio with mathematics



#### Link to mission (SpaceDot - AcubeSAT)



#### How will I go about doing this? (*tools*, different from "resources available")



#### Why I want to do this thesis



#### What I want to do in my MSc (also mention that I want to build the somewhat more "general" skillset; also mention stochastic calculus, dyn. sys (+ differential geometry, manifolds etc.) and nonlinear, complex systems, chaos, just with the application I want)



#### What resources I have at my disposal -> link with MSc (Asteris the friend)




## Proposed Roadmap