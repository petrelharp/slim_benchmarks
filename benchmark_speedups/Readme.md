Max site gain(speedup) vs core count plot for benchmarks from _targeted_tests/ 

## Naming convention:
```<target site>_<model>_<size>.png```

## Target site:
- `int` : integer code part of the sum() in eidos_functions.cpp 
- `float`: float code part of the sum() in eidos_functions.cpp 
- `smt`: SumOfMutationsOfType() in individual.cpp


## Model:

- `omp`:OpenMP
- `tbb`:Thread building blocks

## Size:
Eidos functions are scaled by modifying vector lengths while SMT() is scaled by number of individuals

- `short`: vector length = 5000 ; individuals:1000
- `med`: vector length = 25,000 ; individuals:5000
- `long`: vector length = 650,000 ; individuals:125,000
