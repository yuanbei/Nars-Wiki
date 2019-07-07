Structural rules carry out inference according to the information in the structure of compound terms. For example, NAL-4 introduces relational terms, as well as compound terms with _product_ and _image_ connectors, and consequently, the same conceptual relation can be equivalently expressed in multiple ways.

Consider two premises "Water dissolves salt", i.e. _<(*, water, salt) --> dissolve>_ and "Rain is water", i.e. _<rain --> water>_ one can expect to derive "Rain dissolves salt" by deduction, but it does not fit into the deduction rule defined in NAL-1, since common term _water_ is neither the subject nor the predicate of the first premise but a component of its subject. Therefore some strategy is needed to transform the first premise into something such that deduction can be applied.

### Structural Rules

**Structural Transformation** is a process by which the same statement is equivalently rewritten into other formats, so as to allow a component of the subject term or predicate term of the original statement to be treated as the subject term or predicate term of the new statement, which has the **same truth-value** as the original. 

Thus for a relation _R and a product _(*, T1, T2)_ the following two structural image transformation rules are defined:

**Extensional Image transformation:**<br/>
((*, T1, T2) --> R) <=> (T1 --> (/, R, _, T2)) <=> (T2 --> (/, R, T1, _))

**Intensional Image transformation**:<br/>
(R --> (*, T1, T2)) <=> ((\, R, _, T2) --> T1) <=> ((\, R, T1, _) --> T2)

Where "/" is the extensional image connector, "\" intensional image connector, "\_" symbol indicating the location of _T1_ or _T2_ in the product and "<=>" indicates equivalence.

In the above example, the statement _<(*, water, salt) --> dissolve>_ can be transformed to two other statements:

_water --> (/, dissolve, _, salt)_ <br/>
_salt --> (/, dissolve, water, _)_

Thus water is now appearing in the subject term and not part of a product compound.

Structural transformation rules are also applied when two premises are given to the system and one of them has compound term. System can then deduce one of the below conclusions: <br/>

**1. {S --> P <f1,c1>; (P|Q) <f2,c2>} |-- S --> (P|Q) \<F deduction is applied> <br/> 
2. {S --> P <f1,c1>; (S&T) <f2,c2>} |-- (S&T) --> (P&T) \<F deduction is applied> <br/>
3. {S --> P <f1,c1>; (M-S) <f2,c3>} |-- (M-P) --> (M-S) \<F deduction is applied>** 

Here the second premise is a compound term where "|" means intensional intersection or extensional union; "&" is extensional intersection or intensional union and "-" is intensional difference.

### Types of conceptual relationships

It is important to distinguish three types of conceptual relations present in NARS:
* **Syntactic relation:** A syntactic relation is between a compound term and its components, as the relation between _raven_ and _(-, raven, [black])_. The type of such a relationship is indicated by the term connector of the compound, like the "-" in the above example.
* **Semantic relation:** A semantic relation is between the subject term and the predicate term of a statement, as the relation between _raven_ and _bird_ in _<raven --> bird>_. The type of such a relationship is indicated by the copula, like the "-->" in the above example.
* **Acquired relation:** An acquired relation is among components of a _product_ compound, as the relation between _raven_ and _worm_ in _<(*, raven, worm) --> food>_. The type of such a relationship is indicated by the relational term, like _food_ in the above example.




