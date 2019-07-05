A typical inference rule of NAL takes two premises and derives a conclusion, in the following pattern:<br/>
**_{\<premise1\>. %f1; c1%, \<premise2\>. %f2; c2%} |- \<conclusion\>. %f; c%_**

The truth-value function of the rule calculates _%f; c%_ from _%f1; c1%_ and _%f2; c2%_. According to the definition of truth-value in NAL, the result of the function should correctly indicate the evidential support the conclusion obtained from the premises (alone).

The function is defined in the following procedure:
1. Treat all the variable as binary (Boolean), and analyze how the variables are related to each other, according to the semantics.
2. Find simple and natural Boolean functions to relate these variables.
3. Replace the Boolean operators by their [extended forms](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS)
4. Rewrite the relations as a function that maps _%f1; c1%_ and _%f2; c2%_ to _%f; c%_.

All the truth-value functions are explained in detail in  [Non-Axiomatic Logic](https://www.worldscientific.com/worldscibooks/10.1142/8665), and listed in its [Appendix C](https://doi.org/10.1142/9789814440288_bmatter). There is also [an Excel table](http://www.cis.temple.edu/~pwang/Implementation/NAL/NAL-TruthFunctions.xls) that allows simple experiments with the functions.

As far as the [Basic Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) are concerned, the truth-value functions can be divided into two types:
* Strong inference, including _deduction, analogy_, and _resemblance_, where _c_ has 1 as upperbound;
* Weak inference, including _abduction, induction, exemplification_, and _comparison_, where _c_ has an upperbound _1/(1+k)_ (k is the system parameter introduced in [truth value](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples)).

**Properties:**
* Both frequency and confidence contribute to inference, but in different ways.
* The confidence of a syllogistic conclusion is never higher than the confidence of either premise, that is, confidence “declines” in syllogistic inference.
* Confidence declines much slower in strong inference than in weak inference.
* By switching the order of the premises, another conclusion can be derived from the same pair of premises.