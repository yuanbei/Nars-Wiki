In NARS, many measurements take values from the [0, 1] interval, including all the components of truth-value, desire-value, budget-value, as well as the amount of evidence in single testing. These values are considered as "extended Boolean values", in the sense that the Boolean values in {0, 1} can be taken as special cases of [0, 1]. The Boolean operators **“not”**, **“and”** and **“or”** are extended into the real-number functions defined on [0, 1], too.

### Semantics
Traditionally, the extended “and” and “or” are called **Triangular norm (T-norm)** and **Triangular conorm (T-conorm)**, respectively. Each of them is commutative, associative, and monotonic in each variable and thus they can be extended to take arbitrary number of arguments in the following way:<br/>
__**and**(x1, . . . , xn) = **and**(and(x1, . . . , xn−1), xn)__<br/>
__**or**(x1, . . . , xn) = **or**(or(x1, . . . , xn−1), xn)__

In NARS, T-norm function ***y = and(x1, . . . , xn)*** is used when a quantity ***y*** is __conjunctively__ determined by two or more other quantities __x1, . . . , xn__. For example ***y = 1*** if and only if ***x1 = ... = xn = 1***, and ***y = 0*** if and only if ***x1 = 0 or ... or xn = 0***. 

Similarly, T-conorm function ***y = or(x1, . . . , xn)*** is used when a quantity ***y*** is __disjunctively__ determined by two or more other quantities __x1, ... , xn__. For example, ***y = 1*** if and only if ***x1 = 1 or . . . or xn = 1***, and ***y = 0*** if and only if ***x0 = · · · = xn = 0***. 

Intuitively, a variable ***y*** is __conjunctively__ determined by variables __x1,..., xn__ when all the x’s are its necessary factors, or numerically, if ***y*** is never bigger than any of them. Similarly, ***y*** is __disjunctively__ determined by __x1, . . . , xn__ when all the x’s are its sufficient factors, or numerically, it is never smaller than any of them.
 
### Definition
There are an infinite number of ways of numerically satisfying the prescribed conditions for T-norm and T-conorm. In OpenNARS Boolean functions using "and", "or" and "not" operators are replaced with "T-norm", "T-conorm" and "Negation" functions in the following way:

**Negation:** ***not(x) = 1 − x***<br/>
**T-norm:** ***and(x1, ..., xn) = x1 * ... * xn***<br/>
**T-conorm:** ***or(x1, ..., xn) = 1 − [(1 − x1) * ... * (1 − xn)]***

It should be mentioned that though the T-norm and T-conorm used in OpenNARS share intuition and mathematical forms with probabilistic formula, they should not been understood as and(x, y) = P(x and y) and or(x, y) = P(x or y), simply because x and y are usually not random variables with probability distribution function P.

