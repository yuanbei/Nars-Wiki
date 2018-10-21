OpenNARS operates on logic layers called NALs, there are nine NAL levels (NALs 1-9). NAL levels are added one by one each of which expands the features and capabilities of a previous layer including the [grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), [inference rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) and [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions). Each NAL layer is accompanied with a corresponding Narsese  grammar resulting in 9 Narsese grammars. This article presents each level and briefly describes its features, grammar definition will be omitted from this page instead detailed use of Narsese grammar for each NAL level is outlined [here](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS).

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
4. _Exemplification_ {M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This rule, not discussed by Aristotle or Peirce, in NAL it is called
exemplification, that is basically reversed deduction

NAL-1 introduces key features of OpenNARS: inheritance relation, use of evidence through truth value, inference rules, truth functions and Narsese-1 [grammar]((https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS)). <br/>
1. **Inheritance relation**, “→”, is a relation from one term to another term, defined by being reflexive and transitive but neither symmetric nor anti-symmetric. An inheritance statement consists of two terms related by the inheritance relation. In the inheritance statement “S → P”, S is the **subject** term and P is the **predicate** term. Inheritance relation is closely related to many well-known relations, such as “IS-A” or “belongs to” or “subset”.<br/>
**Example** <snow --> white>.  means snow "is"  white<br/><br/>
2. **Truth value** is a pair of real numbers in the range [0,1] that are called **frequency** and **confidence**.
<br/>**Frequency** is a measurement of uncertainty defined as _positive evidence / total evidence_, while **confidence** measures degree of believe, given _k_ as a temporal constant, might be seen as number of steps taken by the system in the future, confidence _c_ is defined in terms of evidence _w_ as _c = w / (w + k)_, default value for _k_ is 1 <br/>
**Example:** <snow --> white>. %9/10, 10/11% here truth value of frequency=9/10 and confidence=10/11 means that snow has been observed white 9 times and 1 time it was not white, thus the total number of observations, that is **total evidence**, is 10, **positive evidence** is 9/10, since white snow appeared 9 times out of 10, and given that by default _k=1_ confidence, **the measure of believe in positive evidence** is 10/11 that is _total evidence=10_ divided by _total evidence_ plus 1.<br/><br/>
3. Fundamental **[Inference rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)** and **[Truth Functions](https://github.com/opennars/opennars/wiki/Truth-Functions)** used in OpenNARS are described in detail on separate pages, please click on corresponding links

### NAL-2
NAL-2 adds similarity relation, modifies truth functions and introduces sets, instance and property features. 
1. **Similarity**, “↔”, is symmetric inheritance relation. The similarity statement “S ↔ P ” is defined by the conjunction of two inheritance statements (S → P) ∧ (P → S). Therefore, the similarity relation is reflexive, symmetric, and transitive.

2. Because of similarity is symmetric, truth functions are modified:

### _F deduction_

Suppose two premises are  \<S --> M\>.%f1; c1% and \<M --> P\>. %f2; c2%, then using **deduction** syllogistic rule OpenNARS will derive conclusion  \<S -- > P\> %f; c%. 
Truth value of the conclusion is then a simple multiplication of truth values of premises:<br/>

**_F deduction_: f = (f1 * f2) and c = (f1 * c1 * f2 * f2)**
<br/><br/>
A chain of deduction can be formed by more than two judgments, and F deduction can be applied multiple times. For example given premises: _\<a -->b\>. %f1; c1%,  \<b --> c\>. %f2; c2% and  \<c --> d\>. %f3; c3%_, a judgment on _\<a-->d\> %f; c%_ can be formed by applying the deduction rule and _F deduction_ twice.

### _F abduction_

Suppose two premises are  _\<P --> M\>. %f1; c1%_ and _\<S --> M\>.%f2; c2%_ , then using **abduction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f1 * c1* c2_, Therefore:<br/><br/> 
**_F abduction_: f = f2 and c = (f1 * c1 * f2 * f2)/(f1 * c1 * c2 + k)**
<br/>

### _F induction_

This function is symmetric to the abduction one. Suppose two premises are _\<M --> P\>. %f1; c1%_ and _\<M --> S\>.%f2; c2%_; , then using **induction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f2 * c1* c2_, Therefore:<br/><br/> 
**_F induction_: f = f1 and c = (f1 * c1 * f2 * f2)/(f2 * c1 * c2 + k)**
<br/> 

### _F exemplification_

Exemplification can be considered as "reversed deduction" since it derives an inheritance judgment in the opposite direction of deduction. Negative evidence can not be collected in reverse direction of inheritance and thus not present in exemplification.

Suppose two premises are  _\<P --> M\>.%f1; c1%_ and _\<M --> S\>. %f2; c2%_, then using **exemplification** OpenNARS will derive conclusion _\<S --> P\>. %f; c%_ 
Truth value of the conclusion is defined through the positive and total evidence which are equal since no negative evidence can be collected in reverse direction of inheritance. Thus _positive evidence = f1 * c1 * f2 * c2_ = _total evidence = f1 * c1 * f2 * c2_:<br/><br/> 
**_F exemplification_: f = 1 and c = (f1 * c1 * f2 * f2)/(f1 * f2 * c1 * c2 + k)**
<br/> <br/> 

 