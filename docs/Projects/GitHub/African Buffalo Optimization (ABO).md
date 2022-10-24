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

Here, $w_k$ is the `/waaa/` call, which mobilizes the herd to move (explore) with reference to buffalo $k$.
$m_k$ is the `/maaa/` call, which calls to exploit. $w'_k$ is a call for more exploration, while $m_k'$ a call for more exploitation, respectively.
$lp_1$ and $lp_2$ are the so-called learning parameters.
$\lambda$ is a random number which takes any value between $0$ and $1$, depending on the problem being solved; the higher $\lambda$ is, we get more exploitation and less exploration, and vice-versa.

### Math

### References

[[@odiliStochasticProcessTutorial2022]]