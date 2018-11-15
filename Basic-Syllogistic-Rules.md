OpenNARS operates on well known Syllogistic Rules, that provide a foundation to all its logical layers ([NALs](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS)). This page provide a brief overview of logical inference rules of _[deduction](https://en.wikipedia.org/wiki/Deductive_reasoning), [abduction](https://en.wikipedia.org/wiki/Abductive_reasoning), [induction](https://en.wikipedia.org/wiki/Inductive_reasoning) and exemplification_. 

Brief description:
1. _Deduction_: {M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s first figure, and what Peirce called deduction.
2. _Abduction_:  {P → M <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s second figure, and what Peirce called abduction
(and hypothesis)
3. _Induction_ {M → P <f1, c1 >, M → S <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s third figure, and what Peirce called induction
4. _Exemplification_ {M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This rule, not discussed by Aristotle or Peirce, in NAL it is called
exemplification, that is basically reversed deduction
