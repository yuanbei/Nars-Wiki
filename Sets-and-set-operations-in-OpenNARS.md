Sets and set operations are adds more capability to OpenNARS, it allows to combine terms by creating [compound terms](https://github.com/opennars/opennars/wiki/Composition), adds some structure, [tansform that structure](https://github.com/opennars/opennars/wiki/Structure) and as a result derive more complex conclusions.

2. **Set Intersection Definitions**
1. **Compound Terms**

[In Basic Inference](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS), each term is “atomic”, which is named by a word. For more complicated descriptions compound terms added to OpenNARS. 

**Compound term**, (op c(1), c(2), c(3) ... c(n-1), c(n)) is a term formed by one or more terms c(1),..., c(n), called its component, with an operator, op. The order of the components usually matters.
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


4. **Product:** For two terms T1 and T2, their product (T1 × T2) is a compound term defined by ((S1 × S2) → (P1 × P2)) ≡ ((S1 → P1) ∧ (S2 → P2)). This definition can be extended as before to allow more than two components in a product.


5. **Relation as a Term:** A relation is a term R such that there are other terms T1 and T2 satisfying “(T1 × T2) → R” or “R → (T1 × T2)”.<br/>**Example:** “Acid and base neutralize each other” can be represented
as <(* ,acid,base) --> neutralization>., and “Neutralization happens between acid and base” can be represented as <neutralization --> ( *, acid, base)>. where " *" is product operator
<br/><br/>