Basic Inference is a foundation of OpenNARS. It introduces the way OpenNARS process input statements, makes inferences and apply various functions and rules. In the literature this this page is refereed as NAL-1 and NAL-2, a foundation of OpenNARS reasoning principles. 

Logical foundation of OpenNARS reasoning operates on well known [syllogistic inference rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules). It introduces key features of OpenNARS: inheritance and similarity relations, use of evidence through truth value, inference rules, truth functions, property and insistence features and simple Narsese [grammar]((https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS)). <br/>
1. **Inheritance relation**, “→”, is a relation from one term to another term, defined by being reflexive and transitive but neither symmetric nor anti-symmetric. An inheritance statement consists of two terms related by the inheritance relation. In the inheritance statement “S → P”, S is the **subject** term and P is the **predicate** term. Inheritance relation is closely related to many well-known relations, such as “IS-A” or “belongs to” or “subset”.<br/>
**Example** <snow --> white>.  means snow "is"  white<br/><br/>
2. **Truth value** is a pair of real numbers in the range [0,1] that are called **frequency** and **confidence**.
<br/>**Frequency** is a measurement of uncertainty defined as _positive evidence / total evidence_, while **confidence** measures degree of believe, given _k_ as a temporal constant, might be seen as number of steps taken by the system in the future, confidence _c_ is defined in terms of evidence _w_ as _c = w / (w + k)_, default value for _k_ is 1 <br/>
**Example:** <snow --> white>. %9/10, 10/11% here truth value of frequency=9/10 and confidence=10/11 means that snow has been observed white 9 times and 1 time it was not white, thus the total number of observations, that is **total evidence**, is 10, **positive evidence** is 9/10, since white snow appeared 9 times out of 10, and given that by default _k=1_ confidence, **the measure of believe in positive evidence** is 10/11 that is _total evidence=10_ divided by _total evidence_ plus 1.<br/><br/>
3. Fundamental **[Inference rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)** and **[Truth Functions](https://github.com/opennars/opennars/wiki/Truth-Functions)** used in OpenNARS are described in detail on separate pages, please click on corresponding links

4. **Similarity**, “↔”, is symmetric inheritance relation. The similarity statement “S ↔ P ” is defined by the conjunction of two inheritance statements (S → P) ∧ (P → S). Therefore, the similarity relation is reflexive, symmetric, and transitive.
<br/><br/>
**Instance**,“◦→”, is another way to represent the same information. The instance statement “S ◦→ P ” is defined by the inheritance statement “{S} → P ”. The intuitive meaning of “◦→” is similar to the membership relation in set theory. **Example:** “Tweety is a bird” can also be represented as <{Tweety} --> bird>. Meaning that Tweety can be considered as an **instance** of a bird.
<br/><br/>
**Property**,“→◦”, is another way to represent the same information. The property statement “S →◦ P ” is defined by the inheritance statement “S → [P]”. **Example:** "Snow is white" can be represented <snow --> [white]>. meaning snow "is a kind" of white, that is white color is a property of snow.

5. Because of similarity is symmetric, truth functions are modified: 
<br/><br/>
**_F comparison_**<br/>
Suppose two premises are  _\<P --> M\>. %f1; c1%_ and _\<S --> M\>.%f2; c2%_ or _\<M --> P\>. %f1; c1%_ and _\<M --> S\>.%f2; c2%_ then using **comparison** rule OpenNARS will derive conclusion  \<S <--> P\> %f; c%, by comparing the inheritance relations of two terms to a third term. It is easy to see that F comparison is similar to abduction and induction only conclusion is now symmetric.<br/> 
_total evidence w = (f1 + f2 - f1 * f2) * c1 * c2_, and _positive evidence = f1 * c1 * f2 * c2_ Thus, <br/>
**_F comparison_ truth value**: _f = f1*f2/(f1+f2-f1*f2)_ and _c = [c1 * c2 * (f1 + f2 − f1 * f2)]/[c1 * c2 * (f1 + f2 − f1 * f2) + k]_
<br/><br/>
**_F analogy_**<br/> 
Suppose two premises are  _\<S <--> M\>. %f1; c1%_ and _\<M --> P\>.%f2; c2%_ or _\<P --> M\>. %f1; c1%_ and _\<S <--> M\>.%f2; c2%_ then using **analogy** rule OpenNARS will derive conclusion  \<S --> P\> %f; c% or \<P --> S\> %f; c%. The situation is is similar to deduction.Thus, <br/>
**_F analogy_ truth value**: _f = f1*f2_ and _c = c1 * f2 * f2 * c2 * c2_
<br/><br/>
**_F deduction2_**<br/>
Suppose two premises are  _\<S <--> M\>. %f1; c1%_ and _\<M <--> P\>.%f2; c2%_ that is both premises are similarity relations, then using **deduction2** rule OpenNARS will derive conclusion  \<S <--> P\> %f; c%, it can be treated as deduction going in both directions. Thus, <br/>
**_F deduction2_ truth value**: _f = f1*f2_ and _c = c1 * c2 * (f1 + f2 − f1 * f2)_
