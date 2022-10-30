### Introduction

Inspired by the migrant behavior of African buffalos in the vast African landscape.
African buffalos organize their large herds using only two principal sounds.
They navigate the landscape from point A to point B in search of pasture.

They even watched National Geographic documentaries :O

Advantages: fast, robust, effective, efficient, simple to implement/user-friendly; good ability to explore and exploit the search space.

### Addendum: How to develop a swarm intelligence algorithm

1. Observe behavior of group of organisms and note that it realizes objectives impossible for any individual group member
2. Model the behavior
3. Develop a mathematical model based on the behavior model
4. Write pseudocode
5. Implement in code
6. Parameter tuning through mathematical and experimental analysis

### Flowchart

![[abo-flowchart.excalidraw|700]]

1. Initialize the buffalos within the search space.
2. Calculate the buffalo exploitation:
    $m_k' = m_k + lp_1(bg - w_k) + lp_2(bp_k - w_k)$
3. Calculate the buffalo locations:
    $w_k' = \frac{(w_k + m_k)}{\lambda}$
4. Determine if $bg$ is updating. If yes, proceed to $5$. Else, proceed to $2$.
5. Crosscheck stopping criteria. If reached, proceed to $6$. Else, proceed to $2$.
6. Output best solution.

Here, $w_k$ is the `/waaa/` call, which mobilizes the herd to move (explore) with reference to buffalo $k$. $m_k$ is the `/maaa/` call, which calls to exploit. $w'_k$ is a call for more exploration, while $m_k'$ a call for more exploitation, respectively. $bg$ is the buffalo with the best position in relation to the global optimum. $bp_k$ is the buffalo's personal best position. $lp_1$ and $lp_2$ are the so-called learning parameters. $\lambda$ is a random number, called the exploration driver, which takes any value between $0$ and $1$, depending on the problem being solved; the higher $\lambda$ is, we get more exploitation and less exploration, and vice-versa.

### Math

First, randomly initialize the buffalo population within the search space. Next, evaluate buffalo exploitation capacities using $(1)$. This is needed to determine the next move the buffalos are going to take in their search for pastures. $(1)$ is "democratic" and is fed to $(2)$, which describes exploration. This determines whether the buffalo herd will stay in the same location, or whether it will migrate to another location. If the "best" buffalo $bg$ is updating, check whether the stopping criteria have been met. If so, the search has been concluded. Otherwise, go back and reassess the buffalo exploitation values.

Equation $(1)$ is the controlling equation, which propels the entire herd to relocate, on the basis that the new location will probably be more rewarding than the current one:

$$m_k' = m_k + lp_1(bg - w_k) + lp_2(bp_k - w_k) \tag{1}$$

Equation $(1)$ has three parts. First, the memory part ($m_k'$), which reminds the buffalos that they have relocated to a new location from the previous location ($m_k$). Second, the part which signals the cooperative behavior of the buffalos ($lp_1 (bg - w_k)$). Third, part which represents the buffalos capacity for communication across the entire herd ($lp_2(bp_k - w_k)$).

The last (third) part of $(1)$, $lp_2(bp_k - w_k)$, underscores the buffalos intelligence. They can tell which their previous best location was, compared with their current location. This enables them to retrace their steps to the best, to their knowledge, location, which is extremely useful if they stray away towards a starving location. To summarize, equation $(1)$ describes the buffalo memory, ability to harness collective intelligence, and intra-herd communication.

$lp_1$ and $lp_2$ undergo parameter tuning, depending on the problem context. A higher value of $lp_1$ biases the algorithm toward global search while a higher $lp_2$ biases towards a local search.

Equation $(2)$ is what moves the buffalos to the new location, following the decision taken through $(1)$:

$$w_k' = \frac{(w_k + m_k)}{\lambda} \tag{2}$$

$(2)$ shows that the movement of the buffalos is a function of the `/waaa/` ($w_k$) and the `/maaa/` ($m_k$) calls. It's moderated by the exploration driver, $\lambda$, which takes a value between $0$ and $1$.

So, the movement of buffalo $k$ from $w_k$ (present exploration location) to other locations is influenced by $m_k$, the exploitation location, and adjusting its position appropriately in relation to the herd's best $(bg - w_k)$ as well as its personal best ($bp_k - w_k$) with the bias of the learning parameters.

![[abo-visualization.excalidraw|700]]

### Application in 2D



### References

[[@odiliStochasticProcessTutorial2022]]