A syllogistic rule in NAL takes two premises that are statements with a common term, and derive a conclusion with a statement between the other two terms. That is, the two premises are between M--P and S--M, while the conclusion is between S--P. Different types of inference correspond to different combinations of premises and use different truth-value functions to calculate the truth-values of the conclusions from those of the premises.

Here "basic syllogistic rules" refer to those defined in NAL-1 and NAL-2 that use _inheritance_ or _similarity_ copulas.
* Inheritance copula, “-->”, is a relation from one term to another term, defined by being reflexive and transitive (but neither symmetric nor anti-symmetric). An inheritance statement consists of two terms related by the inheritance relation. In the inheritance statement “S --> P”, S is the _subject_ term and P is the _predicate_ term. Inheritance relation is closely related, though not identical, to many well-known relations, such as “IS-A”,  “belongs to”, or “subset”.<br/>
**Example** <swan --> bird>  means "Swan is a type of bird."
* Similarity copula, “<->”, is "two-way inheritance", as it is defined to be reflexive, transitive, and symmetric. The similarity statement “S <-> P ” is defined by the conjunction of two inheritance statements (S → P) ∧ (P → S). **Example** <swan <-> goose>  means "Swan is similar to goose."

There are also three copulas that are only used in external communication, but not in internal representation, as they can be converted into _inheritance_ with the help of the set constructors.
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
OpenNARS operates on well known Syllogistic Rules, that provide a foundation to all its logical layers ([NALs](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS)). Below is a brief overview of logical inference rules of _[deduction](https://en.wikipedia.org/wiki/Deductive_reasoning), [abduction](https://en.wikipedia.org/wiki/Abductive_reasoning), [induction](https://en.wikipedia.org/wiki/Inductive_reasoning) and exemplification_. 

**Brief description:**

Given two judgments on the left (J1 and J2), the conclusion C is derived on the right:
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
