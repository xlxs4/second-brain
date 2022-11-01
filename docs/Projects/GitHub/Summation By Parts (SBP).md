

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

Split between `/dev/MattssonAlmquistVanDerWeide2018...` and `/src/MattssonAlmquistVanDerWeide2018...` .

$x_k$, the non-equidistant grid points in MATLAB (`D1_accurate_8th.m`):
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
