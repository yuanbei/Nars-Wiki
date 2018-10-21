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
**Example** <snow --> white>.  means snow "is"  white
<br/>
2. **Truth value**


