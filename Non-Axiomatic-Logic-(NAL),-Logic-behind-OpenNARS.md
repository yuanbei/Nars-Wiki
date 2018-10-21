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
NAL-2 adds similarity, instance and property relations and modifies truth functions. 
1. **Similarity**, “↔”, is symmetric inheritance relation. The similarity statement “S ↔ P ” is defined by the conjunction of two inheritance statements (S → P) ∧ (P → S). Therefore, the similarity relation is reflexive, symmetric, and transitive.
<br/><br/>
**Instance**,“◦→”, is another way to represent the same information. The instance statement “S ◦→ P ” is defined by the inheritance statement “{S} → P ”. The intuitive meaning of “◦→” is similar to the membership relation in set theory. **Example:** “Tweety is a bird” can also be represented as <{Tweety} --> bird>. Meaning that Tweety can be considered as an **instance** of a bird.
<br/><br/>
**Property**,“→◦”, is another way to represent the same information. The property statement “S →◦ P ” is defined by the inheritance statement “S → [P]”. **Example:** "Snow is white" can be represented <snow --> [white]>. meaning snow "is a kind" of white, that is white color is a property of snow.

2. Because of similarity is symmetric, truth functions are modified: 
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

### NAL-3
NAL-3 introduces compound terms and adds operation on the sets such as set intersection and set difference.
1. In NAL-1 and NAL-2, each term is “atomic”, named by a word. For more complicated descriptions NAL-3 adds compound terms. **Compound term**, (op c(1), c(2), c(3) ... c(n-1), c(n)) is a term formed by one or more terms c(1),..., c(n), called its component, with an operator, op. The order of the components usually matters.
<br/><br/>
If c(1),...,c(n) (n > 2) are terms and _op_ is a term operator, defined as taking two arguments, both (op c(1) ... c(n)) and (c(1) op ... op c(n)) are compound terms defined recursively as (op (op c(1) ... c(n−1)) c(n)).
<br/><br/>
2. **Set Intersection Definitions**
<br/><br/>
**Extensional intersection:** If T1 and T2 are two different terms, their extensional intersection, (T1 ∩ T2), is a compound term defined by _(∀x)(x → (T1 ∩ T2)) ≡ ((x → T1) ∧ (x → T2)))_.<br/>
**Example:** “Ravens are black birds” can be represented as <raven -->(&,[black], bird)>., where the predicate term is an extensional intersection of the term [black] and the term bird, and "&" is an operator for extensional intersection.
<br/><br/>
**Intensional intersection:** If T1 and T2 are different terms, their intensional intersection, (T1 ∪ T2), is a compound term defined by _(∀x)(((T1 ∪ T2) → x) ≡ ((T1 → x) ∧ (T2 → x)))_.<br/>
**Example:** "Dogs and cats are pets" can be expressed as <(|,dog, cat)-->pet>. where "|" is an operator for intensional intersection.
<br/><br/>
3. **Set Difference Definitions**
<br/><br/>
**Extensional Difference:** If T1 and T2 are different terms, their extensional difference, (T1 − T2), is a compound term defined by (∀x)((x → (T1 − T2)) ≡ ((x → T1) ∧ ¬(x → T2))).<br/> **Example:** "Penguins are birds that cannot fly” can be represented as <penguin --> (-, bird, [flying])>., where the predicate term is a extensional difference of the term bird and the term [flying], and "-" is extensional difference operator
<br/><br/>
**Intensional Difference:** If T1 and T2 are different terms, their intensional difference, (T1 ~ T2), is a compound term defined by (∀x)(((T1 ~ T2) → x) ≡ ((T1 → x) ∧ ¬(T2 → x))).<br/> **Example:** "Human are only beings that can speak" can be represented as <(\~, human,being) --> speak>. Where "~" is an intensional difference operator

### NAL-4

NAL-4 allows for "ordinary relations", that are the relations not present in previous NAL layers.
<br/><br/>
1. **Product:** For two terms T1 and T2, their product (T1 × T2) is a compound term defined by ((S1 × S2) → (P1 × P2)) ≡ ((S1 → P1) ∧ (S2 → P2)). This definition can be extended as before to allow more than two components in a product.
<br/><br/>
2. **Relation as a Term:** A relation is a term R such that there are other terms T1 and T2 satisfying “(T1 × T2) → R” or “R → (T1 × T2)”.<br/>**Example:** “Acid and base neutralize each other” can be represented
as <(* ,acid,base)> --> neutralization>., and “Neutralization happens between acid and base” can be represented as <neutralization --> (*, acid, base)>. Where "*" is product operator
<br/><br/>
3. **Image:** For a relation R and a product ( * , T1, T2), the extensional image operator, “/”, and intensional image operator, “\\”, of the relation on the product are defined as the following, respectively:
(( * T1, T2) → R) ≡ (T1 → (/ R o T2))) ≡ (T2 → (/ R T1 o))) and (R → ( * T1 T2)) ≡ ((\\ R o T2)) → T1) ≡ ((\\ R T1 o)) → T2), where ‘o’ is a special symbol indicating the location of T1 or T2 in the product, and in the component list it can appear in any place, except the first (which is reserved for the relational term). <br/>
**Example:** “Acid corrodes metal” can be equivalently represented as <( *, acid, metal) --> corrosion>. <acid → (/, corrosion, o metal)>., and <metal --> (\\, corrosion, acid o)>. Where "o" indicates whether it is T1 or T2 and "/", "\\" are extensional and intensional image operators.