In OpenNARS uncertainty measurements take values from the [0, 1] interval. Even the amount of evidence, which
is not defined with this range in general, corresponds to this interval. Since they cannot be easily interpreted as “probability” as defined in probability theory and statistics, an existing theory cannot be directly applied to guide their calculation. The approach in OpenNARS is to see the values in [0, 1] as extended Boolean values, 0 and 1, and to handle their calculation by extending the Boolean operators, namely **“not”**, **“and”** and **“or”**.

The extended “and” and “or” are called **Triangular norm (T-norm)** and **Triangular conorm (T-conorm)**. T-norm and T-conorm are functions defined on real numbers in range [0, 1]. Each of them is commutative, associative, and monotonic in each variable and thus they can be extended to take arbitrary number of arguments in the following way:<br/>
__**and**(x1, . . . , xn) = **and**(and(x1, . . . , xn−1), xn)__<br/>
__**or**(x1, . . . , xn) = **or**(or(x1, . . . , xn−1), xn)__

In OpenNARS, T-norm function ***y = and(x1, . . . , xn)*** is used when a quantity ***y*** is __conjunctively__ determined by two or more other quantities __x1, . . . , xn__. For example ***y = 1*** if and only if ***x1 = ... = xn = 1***, and ***y = 0*** if and only if ***x1 = 0 or ... or xn = 0***. 

Similarly, T-conorm function ***y = or(x1, . . . , xn)*** is used when a quantity ***y*** is __disjunctively__ determined by two or more other quantities __x1, ... , xn__. For example, ***y = 1*** if and only if ***x1 = 1 or . . . or xn = 1***, and ***y = 0*** if and only if ***x0 = · · · = xn = 0***. 

Intuitively, a variable ***y*** is __conjunctively__ determined by variables __x1,..., xn__ when all the x’s are its necessary factors, or numerically, if ***y*** is never bigger than any of them. Similarly, ***y*** is __disjunctively__ determined by __x1, . . . , xn__ when all the x’s are its sufficient factors, or numerically, it is never smaller than any of them.
 
There are an infinite number of ways of numerically satisfying the prescribed conditions on T-norm and T-conorm. For the current purpose, it is desired for them to be continuous and strictly increasing, so that any
upward (downward) change in any argument will cause an upward (downward) change in the function value.
The above choice is also justifiable in another way. We call quantities
mutually independent of each other, when given the values of any of them,
the remaining ones cannot be determined, or even bounded approximately.
This type of mutual independence among arguments is assumed by the
probabilistic operators, but not by other representative operators, such as
the pair used in fuzzy logic [Bonissone and Decker, 1986]:
and(x, y) = min(x, y); or(x, y) = max(x, y)
As usual, the “not” operator on the extended Boolean variable is defined
by not(x) = 1 − x.
Obviously, to use the probabilistic operators when the mutual independence does not hold (e.g., x = y or x = not(y)) leads to counter-intuitive
results. In the following, the T-norm and T-conorm are only used when the
“mutual independence” condition is satisfied. As far as the two premises
are not based on overlapping evidence, f1, c1, f2, and c2 satisfy this requirement, because given the values of any three of them, the value of the
last one cannot be determined, or even bounded.
It should be mentioned that though the T-norm and T-conorm used in
NARS share intuition and mathematical forms with probabilistic formula,
they should not been understood as and(x, y) = P(x and y) and or(x, y) =
P(x or y), simply because x and y are usually not random variables with
probability distribution function P.

3. To replace the and, or, and not operator in the Boolean function by
the T-norm (and(x, y) = x ∗ y), T-conorm (or(x, y) = 1 − (1 − x)(1 −
74y)), and Negation (not(x) = 1 − x) functions, respectively, so as to
get a general function on [0, 1].