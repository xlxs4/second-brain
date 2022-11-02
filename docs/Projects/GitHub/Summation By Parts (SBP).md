

From [[@mattssonBoundaryOptimizedDiagonalnorm2018]]: 

> The Matlab functions return the differentiation matrix D1, the norm matrix H , the grid point vector x, and the interior grid spacing h. Input to the functions are the grid size m and the width L of the domain.

(`m` is actually `N` in code):
```Matlab
function [D1,H,x,h] = D1_accurate_8th(N,L)
```

| Variable | Definition                |
| -------- | ------------------------- |
| D1       | Differentiation matrix    |
| H        | Norm matrix               |
| x        | Grid (non-equidistant) point vector         |
| h        | Interior grid spacing     |
| m        | Grid size                 |
| L        | Domain length             |
| BP       | Number of boundary points |
| order    | Accuracy of interior stencil                          |

### Julia Implementation

Split between [`/dev/MattssonAlmquistVanDerWeide2018...`](https://github.com/ranocha/SummationByPartsOperators.jl/tree/main/dev) and [`/src/MattssonAlmquistVanDerWeide2018...`](https://github.com/ranocha/SummationByPartsOperators.jl/tree/main/src/SBP_coefficients).

$x_k$, the non-equidistant grid points in MATLAB ([`D1_accurate_8th.m`](https://bitbucket.org/martinalmquist/optimized_sbp_operators/src/master/Accurate/D1_accurate_8th.m)):
```Matlab
%%%% Non-equidistant grid points %%%%%
x0 = 0.0000000000000e+00;
x1 = 3.8118550247622e-01;
x2 = 1.1899550868338e+00;
x3 = 2.2476300175641e+00;
x4 = 3.3192851303204e+00;
x5 = 4.3192851303204e+00;
x6 = 5.3192851303204e+00;
x7 = 6.3192851303204e+00;
x8 = 7.3192851303204e+00;
```
Reside in `/src/`:
```julia
elseif accuracy_order == 8
    xstart = SVector(
      T(0.0000000000000e+00),
      T(3.8118550247622e-01),
      T(1.1899550868338e+00),
      T(2.2476300175641e+00),
      T(3.3192851303204e+00),
      T(4.3192851303204e+00),
      T(5.3192851303204e+00),
      T(6.3192851303204e+00),
      T(7.3192851303204e+00),
    )
```

There is a mention in [[@mattssonBoundaryOptimizedDiagonalnorm2018]] about the $Q$ matrix:

> Definition 2.2: A difference operator $D_1 = H^{-1}Q$, approximating $\partial/\partial x$ using a repeated narrow-stencil in the interior, is said to be a diagonal-norm first-derivative SBP operator if $H$ is diagonal and positive definite, and $Q + Q^T = diag(-1, 0, \ldots, 0, 1)$.

The interior stencil of $Q$ is in MATLAB:
```Matlab
switch order
	case 2
		d = [-1/2,0,1/2];
	case 4
		d = [1/12,-2/3,0,2/3,-1/12];
	case 6
		d = [-1/60,3/20,-3/4,0,3/4,-3/20,1/60];
	case 8
		d = [1/280,-4/105,1/5,-4/5,0,4/5,-1/5,4/105,-1/280];
	case 10
		d = [-1/1260,5/504,-5/84,5/21,-5/6,0,5/6,-5/21,5/84,-5/504,1/1260];
	case 12
		d = [1/5544,-1/385,1/56,-5/63,15/56,-6/7,0,6/7,-15/56,5/63,-1/56,1/385,-1/5544];
end
```
For, e.g. order 8, the relevant part is
```Matlab
	case 8
		d = [1/280,-4/105,1/5,-4/5,0,4/5,-1/5,4/105,-1/280];
```
which can be found in `src/`:
```julia
upper_coef = SVector(T(4//5), T(-1//5), T(4//105), T(-1//280))
lower_coef = -upper_coef
```

For the norm matrix, we have:
```Matlab
P0 = 1.0758368078310e-01;
P1 = 6.1909685107891e-01;
P2 = 9.6971176519117e-01;
P3 = 1.1023441350947e+00;
P4 = 1.0244688965833e+00;
P5 = 9.9533550116831e-01;
P6 = 1.0008236941028e+00;
P7 = 9.9992060631812e-01;
```
which can be found in `dev/`:
```julia
h = [
  1.0758368078310e-01,
  6.1909685107891e-01,
  9.6971176519117e-01,
  1.1023441350947e+00,
  1.0244688965833e+00,
  9.9533550116831e-01,
  1.0008236941028e+00,
  9.9992060631812e-01,
  1, 1, 1, 1]
```
*question*: what about the trailing ones? TODO: how do I determine how many to add?

The boundaries, $Q_k$ are:
```Matlab
...
Q0_0 = -5.0000000000000e-01;
Q0_1 = 6.7284756079369e-01;
Q0_2 = -2.5969732837062e-01;
Q0_3 = 1.3519390385721e-01;
Q0_4 = -6.9678474730984e-02;
Q0_5 = 2.6434024071371e-02;
Q0_6 = -5.5992311465618e-03;
Q0_7 = 4.9954552590464e-04;
Q0_8 = 0.0000000000000e+00;
Q0_9 = 0.0000000000000e+00;
Q0_10 = 0.0000000000000e+00;
Q0_11 = 0.0000000000000e+00;
```
which also reside in `dev/`:
```julia
q1 = [0,
  6.7284756079369e-01,
  -2.5969732837062e-01,
  1.3519390385721e-01,
  -6.9678474730984e-02,
  2.6434024071371e-02,
  -5.5992311465618e-03,
  4.9954552590464e-04,
  0, 0, 0, 0]'
  ```
*question*: in this example, why is the original `Q0_0 = -5.0000000000000e-01;`, while it's `0` in the Julia implementation?

*question*: why `D1 = H \ (Q - 1//2*e*e')` to construct the difference operator $D1$?

*question*: I understand that `dev/` is used first to get the values used in `src/`, e.g. for the `DerivativeCoefficientRow`s. How?
