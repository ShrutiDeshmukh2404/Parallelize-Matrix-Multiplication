# Parallelize-Matrix-Multiplication

Parallel Matrix Multiplication with Static Scheduling:
#include <omp.h>: Includes OpenMP library functions, which allow us to use OpenMP directives for parallelization.
The other includes and macro definitions are the same as in the serial version.
#pragma omp parallel for schedule(static): This directive tells the compiler to parallelize the for loop that follows using OpenMP. The schedule(static) clause ensures that the iterations of the loop are divided evenly across all available threads.
Static scheduling assigns a fixed number of iterations to each thread before execution begins, reducing scheduling overhead.
The rest of the function remains the same as the serial version, but now the outer loop (i) is parallelized, allowing multiple threads to work on different rows of the matrices simultaneously.
The main() function is almost identical to the serial version. The only difference is that it calls matrix_multiply_static() for parallelized matrix multiplication.
The execution time of the static scheduling version is printed.


Parallel Matrix Multiplication with Dynamic Scheduling:
#pragma omp parallel for schedule(dynamic): This directive parallelizes the for loop and applies dynamic scheduling. In dynamic scheduling, iterations of the loop are assigned to threads in chunks as threads become available. This is useful when the amount of work per iteration is not uniform, as it helps balance the load across threads.
The function body is identical to the static scheduling version, except for the scheduling policy.
Similar to the static version, except it calls matrix_multiply_dynamic() to perform matrix multiplication with dynamic scheduling.
