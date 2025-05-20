# Benchmark Results Summary

All benchmarks were run with input size parameter `1000`. The results include time taken for elimination and solving, along with variable and atom counts before and after elimination.

---

## `benchmark_dickson_int`
- **Elimination Time**: 713.14 ms  
- **Input**: 2000 variables, 4000 atoms  
- **Output**: 22000 variables, 19002 atoms  
- **Satisfiable**: ❌  
- **Solving Time**: 15880.62 ms  

---

## `benchmark_equal_exists_2_int`
- **Elimination Time**: 2113.47 ms  
- **Input**: 3000 variables, 3000 atoms  
- **Output**: 26000 variables, 27000 atoms  
- **Satisfiable**: ✅  
- **Solving Time**: 7552.76 ms  

---

## `benchmark_equal_exists_int`
- **Elimination Time**: 1186.14 ms  
- **Input**: 3000 variables, 2000 atoms  
- **Output**: 17000 variables, 17000 atoms  
- **Satisfiable**: ✅  
- **Solving Time**: 3895.67 ms  

---

## `benchmark_equal_free_2_int`
- **Elimination Time**: 1127.98 ms  
- **Input**: 3000 variables, 3000 atoms  
- **Output**: 18000 variables, 14002 atoms  
- **Satisfiable**: ❌  
- **Solving Time**: 1996.26 ms  

---

## `benchmark_equal_free_int`
- **Elimination Time**: 399.73 ms  
- **Input**: 3000 variables, 2000 atoms  
- **Output**: 9000 variables, 8001 atoms  
- **Satisfiable**: ❌  
- **Solving Time**: 939.56 ms  

---

## `benchmark_half_int` *(with extra arg 50)*
- **Elimination Time**: 371.88 ms  
- **Input**: 2000 variables, 2000 atoms  
- **Output**: 12000 variables, 10002 atoms  
- **Satisfiable**: ❌  
- **Solving Time**: 1523.15 ms  



---



# Old
## `benchmark_dickson_int`
- **Elimination Time**: 1,833,742 ms  
- **Solving Time**: 300,390 ms  
- **Input**: 2000 variables, 5000 atoms  
- **Output**: 37000 variables, 226000 atoms  
- **Satisfiable**: ❌  

---

## `benchmark_equal_exists`
- **Elimination Time**: 4,368,956 ms  
- **Solving Time**: 76,216 ms  
- **Input**: 3000 variables, 2000 atoms  
- **Output**: 31000 variables, 166000 atoms  
- **Satisfiable**: ✅  

---

## `benchmark_equal_free`
- **Elimination Time**: 1,575,669 ms  
- **Solving Time**: 6,484 ms  
- **Input**: 3000 variables, 2000 atoms  
- **Output**: 28000 variables, 162000 atoms  
- **Satisfiable**: ❌  

---

## `benchmark_half_int`
- **Elimination Time**: 885,420 ms  
- **Solving Time**: 5,218 ms  
- **Input**: 2000 variables, 2000 atoms  
- **Output**: 22000 variables, 130000 atoms  
- **Satisfiable**: ❌  
