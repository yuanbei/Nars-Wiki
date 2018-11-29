Compound Terms, Set Operations and **compositional rules** are introduced in NAL-3 and briefly mentioned on [NAL page](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) however since it is one of the major aspect of reasoning in OpenNARS they are described here in more detail.

### Compound Terms and syntactic complexity/simplicity

Before rules are established themselves Compound terms needed to be specified, basically compound terms are term that consists from multiple components or formally: <br/> _A compound term (con C1,...,Cn) is a term formed by a term connector, con, that **connects** one or more terms that are called the components of the compound._ <br/>Term connector is a logical constant with no internal structure and connectors are predefined as part of NALs. The order of the components does matter, and the components are allowed to be same. Two compound terms are identical if they have the same term connector and pairwise identical components.

Since compound terms may have compound within themselves some hierarchy has been established: Each term has attached **syntactic complexity**, an integer number. The **syntactic complexity** of an atomic term is 1, while syntactic complexity of a compound term is 1 plus the sum of syntactic complexities of its components. Thus, the syntactic complexity of a compound term is just the number of  words and connectors within its structure, and of course the process is recursive. 

The opposite to syntactic complexity is **syntactic simplicity** that is defined as is s = 1/(n^r), where n is syntactic complexity and r > 0 is a system parameter. Since n ≥ 1, s is in (0, 1]. Atomic terms have the highest simplicity, 1.0 since their complexity is 1.

**Syntactic simplicity** is necessary when [Choice rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) is applied to selective question of the form "S => ?" or "? ==> P" and S and/or P are compound terms, the system strives to use the answer that has lowest syntactic simplicity since it will use less system resources to process.

### Intensinal/Extensional Intersection and difference

**Extensional intersection:** Given terms T1 and T2, their extensional intersection (T1 ∩ T2) is a compound term defined by (∀x)((x --> (T1 ∩ T2)) <--> ((x --> T1) ^ (x --> T2)))
This means that if it a term x has inheritance relation with with (T1 ∩ T2) then it it has separate inheritance relations  with T1 and T2 

**Intensional intersection:** Given terms T1 and T2, their intensional intersection (T1 ∪ T2) is a compound term defined by (∀x)(((T1 ∪ T2) --> x)) <--> ((T1 --> x ) ^ (T2 --> x)))

**Extensional Difference:** Given different terms T1 and T2, their extensional difference (T1 - T2) is a compound term defined by (∀x)((x --> (T1 - T2)) <--> ((x --> T1) ^ ¬(x --> T2))) Meaning there is a inheritance relationship x --> (T1 - T2) and x --> T1 but there is **no** inheritance x --> T2

**Intensional difference:** Given different  terms T1 and T2, their intensional difference (T1 ⊖ T2) is a compound term defined by (∀x)(((T1 ⊖ T2) --> x)) <--> ((T1 --> x ) ^ ¬(T2 --> x)))

### Compositional rules

Compound terms can be introduced as they are into system's experience or built from non-compound existing terms using **Compositional rules**.
There are the following compositional rules:

**Extensional Intersection/Difference** <br/>
{T1 --> M <f1, c1>, T2 --> M <f2, c2>} |-- (T1 ∪ T2) --> M < F union is applied> <br/>
{T1 --> M <f1, c1>, T2 --> M <f2, c2>} |-- (T1 ∩ T2) --> M < F intersection is applied> <br/>
{T1 --> M <f1, c1>, T2 --> M <f2, c2>} |-- (T1 ⊖ T2) --> M < F difference is applied> <br/>
{T1 --> M <f1, c1>, T2 --> M <f2, c2>} |-- (T1 ⊖ T2) --> M < F' difference is applied> <br/>

**Extensional Intersection/Difference** <br/>
{M --> T1 <f1, c1>, M --> T2 <f2, c2>} |-- M --> (T1 ∩ T2) <F intersection is applied> <br/>
{M --> T1 <f1, c1>, M --> T2 <f2, c2>} |-- M --> (T1 ∪ T2) <F union is applied> <br/>
{M --> T1 <f1, c1>, M --> T2 <f2, c2>} |-- M --> (T1 - T2) <F difference is applied> <br/>
{M --> T1 <f1, c1>, M --> T2 <f2, c2>} |-- M --> (T1 - T2) <F' difference is applied> <br/>
<br/>

Please see that in the above rules the conclusion is not between  two **unshared** terms in the premises instead it is happening between the shared term and a compound term composed by the other two. Therefore these rules are referred as compositional rather than syllogistic, however the truth value of a conclusion is being computed using same truth functions as syllogistic rules. Also important aspect that terms T1 and T2 are different and premises cannot have overlapping evidential bases. 

Three truth-value functions used in compositional rules are decribed below:

**F intersection:** f = and(f1, f2) c = and(c1, c2) <br/>
**F union:** f = or(f1, f2) c = and(c1, c2) <br/>
**F difference:** f = and(f1, not(f2)) c = and(c1, c2) <br/>

In these functions, the frequency of the conclusion is determined by the frequency of the premises with the same Boolean operator that defines extension or intension of the compound term, while the confidence of the conclusion is determined conjunctively by the confidence of the premises.



