# Fibonacci Numbers

By changing symbol N, can configure to print out the first N (up to 44) fibonacci numbers.

    1. Runs in 1346 cycles for N=44
    2. Uses at most 260 MIX bytes of memory

Uses double buffer approach like that of Knuth's Program P, effectively allowing for 
concurrent printing as it processes the fibonacci numbers.

### High Level Overview

Calculates the fibonacci numbers by storing Fib(n-1) and Fib(n) in memory locations 
3000 and 3001 respectively, where n is the last calculated Fibonacci number.
To calculate the next number, we simply add Fib(n-1) and Fib(n) to get Fib(n+1),
store Fib(n) where Fib(n-1) was and Fib(n+1) where Fib(n) was.

In a loop it will calculate the next fibonacci number, convert it to its character 
representation, and then store it in the next available locations in the current buffer.
When the buffer is full, it begins printing of the buffer and the loop continues storing 
numbers in the other buffer. When said buffer is full, it switches back to the first buffer, 
and so on.
