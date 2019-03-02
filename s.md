I have introduced several uncertainty measurements, and most of them
take values from the [0, 1] interval. Even the amount of evidence, which
is not defined with this range in general, corresponds to this interval when
it is limited to a piece of evidence within a unit amount. Since they cannot be easily interpreted as “probability” as defined in probability theory
and statistics, we cannot directly apply an existing theory to guide their
calculation in the truth-value functions attached to various inference rules.
After exploring several possibilities, the approach used in NARS is to
see the values in [0, 1] as extended Boolean values, 0 and 1, and to handle
their calculation by extending the Boolean operators, namely “not”, “and”,
and “or”.
The extended “and” and “or” are often called Triangular norm (Tnorm) and Triangular conorm (T-conorm), respectively. T-norm and Tconorm are functions defined on real numbers in [0, 1]. Each of them is
both commutative and associative, and monotonic in each variable. Tnorm has boundary conditions satisfying the truth tables of the logical
operator “and”, and T-conorm those of “or”. [Bonissone and Decker, 1986,
Dubois and Prade, 1982, Schweizer and Sklar, 1983]
In this book, these two functions are directly written as and(x1, x2) and
or(x1, x2). Because each is commutative and associative, each of them can
72be extended to take an arbitrary number of arguments in the following way:
and(x1, . . . , xn) = and(and(x1, . . . , xn−1), xn),
or(x1, . . . , xn) = or(or(x1, . . . , xn−1), xn).
The usage of T-norm and T-conorm in NARS is different from that in
other approaches [Bonissone and Decker, 1986, Dubois and Prade, 1982],
where they are used to determine the degree of certainty of the conjunction
and disjunction of two propositions, respectively. In NARS, the T-norm
function y = and(x1, . . . , xn) is used when a quantity y is conjunctively
determined by two or more other quantities x1, . . . , xn — that is, y = 1 if
and only if x1 = · · · = xn = 1, and y = 0 if and only if x1 = 0 or . . . or
xn = 0; similarly, the T-conorm function y = or(x1, . . . , xn) is used when
a quantity y is disjunctively determined by two or more other quantities
x1, . . . , xn — that is, y = 1 if and only if x1 = 1 or . . . or xn = 1, and y = 0
if and only if x0 = · · · = xn = 0. These functions are not directly about
the conjunction or disjunction of NAL judgments.
Intuitively, a variable y is conjunctively determined by variables x1,
. . ., xn when all the x’s are its necessary factors, or numerically, if y is
never bigger than any of them. Similarly, y is disjunctively determined
by x1, . . . , xn when all the x’s are its sufficient factors, or numerically, it
is never smaller than any of them. In this way, T-norm and T-conorm
are applied in situations where a quantity is determined by several factors,
where we wish the boundary condition to be satisfied, and where no one
factor is more important than any of the others.
There are an infinite number of ways of numerically satisfying the prescribed conditions on T-norm and T-conorm. For the current purpose, it
is desired for them to be continuous and strictly increasing, so that any
upward (downward) change in any argument will cause an upward (downward) change in the function value. In [Schweizer and Sklar, 1983] it is
proved that all functions satisfying the above conditions are isomorphic to
(i.e., can be represented as a monotonic transform of) the “probabilistic”
operators:
and(x, y) = xy; or(x, y) = x + y − xy.
It is also shown in [Bonissone and Decker, 1986] that only a small finite
subset of the infinite set of possible T-norms and T-conorms will produce
significantly different results, if we limit our concern to the “finest level of
distinction among different quantifications of uncertainty”. Among those
representative operators in the small subset, the above pair is the only
continuous and strict T-norm and T-conorm. The Schweizer–Sklar and
Bonissone–Decker results show that the above T-norm and T-conorm have
73not been chosen arbitrarily for NARS; although in principle there are other
pairs satisfying our requirements, they are usually more complex, and are
not significantly different from the above pair.
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
In NAL, the truth-value function for most of the inference rules (with
the previously defined revision and choice as exceptions) are built by the
following steps:
1. To treat all the uncertainty values involved as Boolean variables whose
value are either 0 or 1. According to the definition of these uncertainty
measurements and the semantics of Narsese, the uncertainty values
of the conclusion is determined for each combination of those of the
premises.
2. To represent the uncertainty values of the conclusion as Boolean expressions of the the uncertainty values of the premises that satisfy the
above boundary conditions. Usually there are infinitely many function that satisfy the restriction, and the ones accepted are those that
are simple and have natural interpretations.
3. To replace the and, or, and not operator in the Boolean function by
the T-norm (and(x, y) = x ∗ y), T-conorm (or(x, y) = 1 − (1 − x)(1 −
74y)), and Negation (not(x) = 1 − x) functions, respectively, so as to
get a general function on [0, 1].