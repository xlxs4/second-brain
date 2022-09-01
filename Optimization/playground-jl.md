
```julia
##
using Plots
##

##
function fplot(f, x::AbstractRange=-5.0:0.05:5.0, y::AbstractRange=-5.0:0.05:5.0)
    z = Surface((x, y) -> f([x, y]), x, y)

    plotlyjs()
    p = surface(x, y, z, c = :acton, linealpha = 0.3, legend = false, yshowaxis = false, background_color = :transparent)
    return p
end
##

##
function splot(p, dirname::AbstractVector{String}, filename)
    savefig(p, joinpath(dirname..., filename))
end

function splot(p, dirname::AbstractString, filename)
    savefig(p, joinpath(dirname, filename))
end

function splot(p, filename)
    savefig(p, filename)
end
##

##
function f(x::Vector)
    return 9 - 2x[1] + 4x[2] - x[1]^2 - 4x[2]^2
end
##

##
splot(fplot(f), "17-06-2020-opt.png")
##

##
function f(x::Vector)
    return 12x[1]^2 -8x[1]x[2] + 12x[2]^2
end
##

##
splot(fplot(f), "17-09-2021-opt.png")
##

##
function rosenbrock(x::Vector)
    return 100*(x[2] - x[1]^2)^2 + (1 - x[1])^2
end
##

##
splot(fplot(rosenbrock, -1.0:0.005:1.0, -1.0:0.005:1.0), "06-04-2022-rosenbrock-opt.png")
##
```
