A syllogistic rule in NAL takes two premises that are statements with a common term, and derive a conclusion with a statement between the other two terms. That is, the two premises are between M--P and S--M, while the conclusion is between S--P. Different types of inference correspond to different combinations of premises and use different truth-value functions to calculate the truth-values of the conclusions from those of the premises.

Here "basic syllogistic rules" refer to those defined in NAL-1 and NAL-2 that use _inheritance_ or _similarity_ copulas.
* **Inheritance**, “-->”, is a relation from one term to another term, defined by being reflexive and transitive (but neither symmetric nor anti-symmetric). An inheritance statement consists of two terms related by the inheritance relation. In the inheritance statement “S --> P”, S is the _subject_ term and P is the _predicate_ term. Inheritance relation is closely related, though not identical, to many well-known relations, such as “IS-A”,  “belongs to”, or “subset”.<br/>
**Example:** <swan --> bird>  means "Swan is a type of bird."
* **Similarity**, “<->”, is "two-way inheritance", as it is defined to be reflexive, transitive, and symmetric. The similarity statement “S <-> P ” is defined by the conjunction of two inheritance statements (S --> P) and (P --> S).<br/> 
**Example:** <swan <-> goose> means "Swan is similar to goose."

The syllogistic rules defined on _inheritance_ and _similarity_ include the following types:
* _Deduction_: {M --> P, S --> M} |- S --> P
* _Abduction_:  {P --> M, S --> M} |- S --> P
* _Induction_: {M --> P, M --> S} |- S --> P
* _Exemplification_: {P --> M, M --> S} |- S --> P
* _Comparison_: {M --> P, M --> S} |- S <-> P
* _Analogy_: {M --> P, S <-> M} |- S --> P
* _Resemblance_: {M <-> P, S <-> M} |- S <-> P

The truth-value functions of these rules are explained in the [Truth Function](https://github.com/opennars/opennars/wiki/Truth-Functions) page.

The above list shows an important "triangularity" among the rules: for any three judgments J1, J2, and J3, if J3 can be derived from J1 and J2 by a syllogistic rule, then from J3 and J1 the system can generate J2', which has
the same statement as J2 however possibly with different truth values. 

There are also three copulas that are only used in the external communication, but not in the internal representation, of the system, as they can be converted into _inheritance_ with the help of the set constructors.
* **Instance**, "{--" indicates an inheritance-like relation where the subject term is specified by its single instance, similar to the membership relation in set theory. The instance statement “S {-- P ” is defined as being equivalent to the inheritance statement “{S} --> P". <br>
**Example:** “Tweety is a bird” can be represented as both <Tweety {-- bird> and <{Tweety} --> bird>, though the former is converted into the latter at the interface.
* **Property**, "--]" indicates an inheritance-like relation where the predicate term is specified by its single property, similar to the predicate symbol in predicate logic. The instance statement “S --] P ” is defined as being equivalent to the inheritance statement “S --> [P]". <br>
**Example:** “Snow is white” be represented as both <snow --] white> and <snow --> [white]>, though the former is converted into the latter at the interface.
* **Instance-Property**, "{-]", is the combination of the above two, so "S {-] P" is equivalent to "{S} --> [P]".<br/>
**Example:** “Tweety is yellow” can be represented as both <Tweety {-] yellow> and <{Tweety} --> [yellow]>, though the former is converted into the latter at the interface.

These three copulas are not directly processed by the inference rules.