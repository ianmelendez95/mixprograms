# Program P

This is my own attempt roughly from scratch of implementing Knuth's Program P, which simply
prints out the first 50 prime numbers.

    1. runs in 192096 cycles (Knuth's runs at 190908, %0.62 improvement)

History

[2020-07-06] Ran in 227278, but now skip checking prime divisor 2 and trimmed unconditional jumps,
running in 192096
