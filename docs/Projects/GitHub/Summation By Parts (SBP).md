

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