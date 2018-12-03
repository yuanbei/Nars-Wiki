Structural rules are introduced when sentence becomes larger in structure. With NAL-3 compound terms, sets and set operations are introduced that allows creation of more sophisticated structure for both term and sentences that leads to [compositional rules](https://github.com/opennars/opennars/wiki/Composition). NAL-4 Introduce relations on top of sets and its operation leading to structural transformation and manipulation.

It is important to mention three types of relations present in OpenNARS

**Syntactic relation:** A syntactic relation is between a compound term and its components, like the relation between raven and (raven − [black]). These relations are indicated by the term connector of the compound "-" <br/>

**Semantic relation:** A semantic relation is between the subject term and the predicate term of a statement, like the relation between raven and bird in <raven --> bird>. These relations are indicated by the copula "-->" of the statement<br/>

**Acquired relation:** An acquired relation is among components of a product, like the relation between raven and worm in <(*,raven, worm) --> food>. <br/>

Consider example of reasoning: Having two premises "water dissolves salt i.e. <(*,water,salt) --> dissolve>" and "rain is water <rain --> water>" one can expect to derive "rain dissolves salt" by deduction, but it does not fit into deduction rule defined in first order inference since common term water is neither the subject nor the predicate of the first premise but a component of its subject. Therefore some strategy is needed to transform first premise into something such that deduction can be applied.

### Structural Rules

**Structural Transformation** is a process by which the same statement is equivalently rewritten into other formats, so as to allow a component of the subject term or predicate term of the original statement to be treated as the subject term or predicate term of the new statement, which has the **same truth-value** as the original. 

Thus for a relation R and a product (× T1, T2) the following two structural image transformation rules are defined:

**Extensional Image transformation:**<br/>
((× T1, T2) --> R) <=> (T1 --> (/R  T2)) <=> (T2 --> (/R T1 ◇))

**Intensional Image transformation**:<br/>
(R --> (× T1, T2)) <=> ((\R, ◇ T2) --> T1) <=> ((\R, T1 ◇) --> T2)

Where "/" is the extensional image connector, "\" intensional image connector, "◇" symbol indicating location of T1 or T2 in the product and <=> indicates equivalence.

In the above example product term "(water x salt) --> dissolve" can be transformed to two statements:

water --> (/dissolve ◇ salt) <br/>
salt --> (/ dissolve water ◇)

Thus water is now appearing in the subject term and not part of a product compound.

Structural rules are also applied when two premises are given to the system and one of them has compound term. System can then deduce one of the below conclusions: <br/>

**1. {S --> P <f1,c1>; (P|Q) <f2,c2>} |-- S --> (P|Q) <F deduction is applied> <br/> 
2. {S --> P <f1,c1>; (S&T) <f2,c2>} |-- (S&T) --> (P&T) <F deduction is applied> <br/>
3. {S --> P <f1,c1>; (M-S) <f2,c3>} |-- (M-P) --> (M-S) <F deduction is applied>** 

Here the second premise is a compound term where "|" means intensional intersection or extensional union; "&" is extensional intersection or intensional union and "-" is intensional difference.





