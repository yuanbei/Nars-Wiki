OpenNARS operates on logic layers called NALs, there are nine NAL levels (NALs 1-9). NAL levels are added one by one each of which expands the features and capabilities of a previous layer including the [grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), inference rules and [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions). This article presents each level and briefly describes its features.

In general nine NAL levels are divided into two groups: **First-Order Inference (NALs 1-4)** and **Higher-Order Inferences (NALs 5-9)**

## First-Order Inference (NALs 1-4)
### NAL-1

NAL-1 is a logical foundation of OpenNARS, it operates on well known logical inference rules of _[deduction](https://en.wikipedia.org/wiki/Deductive_reasoning), [abduction](https://en.wikipedia.org/wiki/Abductive_reasoning), [induction](https://en.wikipedia.org/wiki/Inductive_reasoning) and exemplification_. 

Brief description
1. _Deduction_: {M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s first figure, and what Peirce called deduction.
2. _Abduction_:  {P → M <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s second figure, and what Peirce called abduction
(and hypothesis)
3. _Induction_ {M → P <f1, c1 >, M → S <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s third figure, and what Peirce called induction
4. {M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This rule, not discussed by Aristotle or Peirce, in NAL it is called
exemplification, basically reversed deduction

NAL-1 introduces key features of OpenNARS: inheritance relation, use of evidence through truth value, inference rules, truth functions and Narsese-1 grammar. <br/>
1. **Inheritance relation**, “→”, is a relation from one term to another term, defined by being reflexive and transitive but neither symmetric nor anti-symmetric. An inheritance statement consists of two terms related by the inheritance relation. In the inheritance statement “S → P”, S is the **subject** term and P is the **predicate** term. Inheritance relation is closely related to many well-known relations, such as “IS-A” or “belongs to” or “subset”.<br/>
**Example** <snow --> white>.  means snow "is"  white<br/><br/>
2. **Truth value** is a pair of real numbers in the range [0,1] that are called **frequency** and **confidence**.
<br/>**Frequency** is a measurement of uncertainty defined as _positive evidence / total evidence_, while **confidence** measures degree of believe, given _k_ as a temporal constant, might be seen as number of steps taken by the system in the future, confidence _c_ is defined in terms of evidence _w_ as _c = w / (w + k)_, default value for _k_ is 1 <br/>
**Example:** <snow --> white>. %9/10, 10/11% here truth value of frequency=9/10 and confidence=10/11 mean that snow has been observed white 9 times and 1 time it was not white, thus the total number of observations, that is **total evidence**, is 10, **positive evidence** is 9/10, since white snow appeared 9 times out of 10, and given that by default _k=1_ confidence, **the measure of believe in positive evidence** is 10/11 that is _total evidence=10_ divided by _total evidence_ plus 1.
<br/>
3. Fundamental **Inference rules** and **Truth Functions** used in OpenNARS are described on separate pages.<br/>