Sets and set operations allow the system to specify instances or properties of a concept, as well as to create [compound terms](https://github.com/opennars/opennars/wiki/Composition), so as to express and derive more complex conclusions.

#### **Compound Terms**
[In Basic Syllogistic Inference](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules), each term is “atomic”, named by a word. For more complicated descriptions, compound terms are added to NAL. 

Compound term _(op c1, c2,..., cn)_ is a term formed by one or more terms _c1, c2,..., cn_, called its components, with an operator, _op_. The order of the components usually matters.
<br/>
Each term in NARS has a _syntactic complexity_ that is completely defined according to its internal structure: atomic terms (such as a word) have complexity value of 1, and a compound's complexity is the sum of the complexity values of its components plus 1 (for the operator). 

#### **Set Intersection Definitions**
**Extensional intersection:** If _T1_ and _T2_ are different terms, their extensional intersection, _(&, T1, T2)_, is a compound term defined by _(∀x)(x --> (&, T1, T2)) ≡ ((x --> T1) ∧ (x --> T2)))_.<br/>
**Example:** “Ravens are black birds” can be represented as _<raven --> (&, [black], bird)>_, where the predicate term is an extensional intersection of the term _[black]_ and the term _bird_, i.e., its extension is the intersection of the extensions of its components, and its intension is the union of the intensions of its components.
<br/><br/>
**Intensional intersection:** If _T1_ and _T2_ are different terms, their intensional intersection, _(|, T1, T2)_, is a compound term defined by _(∀x)(((|, T1, T2) --> x) ≡ ((T1 --> x) ∧ (T2 --> x)))_.<br/>
**Example:** "Dogs and cats are pets" can be expressed as _<(|, dog, cat) --> pet>_, where the subject term is an intensional intersection of the term _dog_ and the term _cat_, i.e., its intension is the intersection of the intensions of its components, and its extension is the union of the extensions of its components.

#### **Set Difference Definitions**
**Extensional Difference:** If _T1_ and _T2_ are different terms, their extensional difference, _(-, T1, T2)_, is a compound term defined by _(∀x)((x --> (-, T1, T2)) ≡ ((x --> T1) ∧ ¬(x --> T2)))_.<br/> 
**Example:** "Penguins are birds that cannot fly” can be represented as _<penguin --> (-, bird, [flying])>_, where the predicate term is an extensional difference of the term _bird_ and the term _[flying]_, i.e., its extension is the difference of the extensions of its components, and its intension is the intensions of its first component.
<br/>
**Intensional Difference:** If _T1_ and _T2_ are different terms, their intensional difference, _(~, T1, T2)_, is a compound term defined by 
_(∀x)(((~, T1, T2) --> x) ≡ ((T1 --> x) ∧ ¬(T2 --> x)))_<br/>
**Example:** "Dogs differ from the other pets by their loyalty" can be represented as _<(~, dog, pet) --> [loyal])>_, where the subject term is an intensional difference of the term _dog_ and the term _pet_, i.e., its intension is the difference of the intensions of its components, and its extension is the extensions of its first component.
<br/>

#### Product and relational term
For two terms _T1_ and _T2_, their product _(*, T1, T2)_ is a compound term defined by _((*, S1, S2) --> (*, P1, P2)) ≡ ((S1 --> P1) ∧ (S2 --> P2))_. This definition can be extended to allow more than two components in a product.
<br/>
A relation is a term _R_ such that there are other terms _T1_ and _T2_ satisfying _(*, T1, T2) --> R_ or _R --> (*, T1, T2)”.<br/>
**Example:** “Acid and base neutralize each other” can be represented as _<(*, acid, base) --> neutralization>_, and “Neutralization happens between acid and base” can be represented as _<neutralization --> (*, acid, base)>_. 