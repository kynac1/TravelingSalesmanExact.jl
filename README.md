# TSP_MIP

[![Dev](https://img.shields.io/badge/docs-dev-blue.svg)](https://ericphanson.github.io/TSP_MIP.jl/dev)
[![Build Status](https://travis-ci.com/ericphanson/TSP_MIP.jl.svg?branch=master)](https://travis-ci.com/ericphanson/TSP_MIP.jl)

This is a simple Julia package to solve the travelling saleman problem in the symmetric case using an Dantzig-Fulkerson-Johnson algorithm. I learned about this kind of algorithm from the very nice blog post <http://opensourc.es/blog/mip-tsp> which also has a [Julia implementation](https://github.com/opensourcesblog/mip_tsp). The implementation in this package uses the symmetry of the problem to reduce the number of variables, and is a simple version of the algorithm described by (Pferschy and Staněk, 2017).

See also [TravelingSalesmanHeuristics.jl](https://github.com/evanfields/TravelingSalesmanHeuristics.jl) for a Julia implementation of heuristic solutions to the TSP (which will be much more performant, especially for large problems, although not exact).

>Generating subtour elimination constraints for the TSP from pure integer solutions  
>Pferschy, U. & Staněk, R. Cent Eur J Oper Res (2017) 25: 231. 
><https://doi.org/10.1007/s10100-016-0437-8>


>Solution of a Large-Scale Traveling-Salesman Problem  
>G. Dantzig, R. Fulkerson, and S. Johnson, 	J. Oper. Res. Soc. (1954) 2:4, 393-410  
><https://doi.org/10.1287/opre.2.4.393>

## Usage


Requires Julia (<https://julialang.org/downloads/>).

To install the package, add the package from GitHub:
```julia
] add https://github.com/ericphanson/TSP_MIP.jl
```

### Example

```julia
using TSP_MIP
n = 50
cities = [ [rand(1.0:100.0), rand(1.0:100.0)] for _ in 1:n];
results = get_optimal_tour(cities)
```

![Example](example.svg)