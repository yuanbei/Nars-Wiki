Compound Terms, Set Operations and **compositional rules** are introduced in NAL-3 and briefly mentioned on [NAL page](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) however since it is one of the major aspect of reasoning in OpenNARS they are described here in more detail.

Before rules are established themselves Compound terms needed to be specified, basically compound terms are term that consists from multiple components or formally: <br/> _A compound term (con C1,...,Cn) is a term formed by a term connector, con, that **connects** one or more terms that are called the components of the compound._ <br/>Term connector is a logical constant with no internal structure and connectors are predefined as part of NALs. The order of the components does matter, and the components are allowed to be same. Two compound terms are identical if they have the same term connector and pairwise identical components.

Since compound terms may have compound within themselves some hierarchy has been established: Each term has attached **syntactic complexity**, an integer number. The **syntactic complexity** of an atomic term is 1, while syntactic complexity of a compound term is 1 plus the sum of syntactic complexities of its components. Thus, the syntactic complexity of a compound term is just the number of  words and connectors within its structure, and of course the process is recursive. 

The opposite to syntactic complexity is **syntactic simplicity** that is defined as is s = 1/(n^r), where n is syntactic complexity and r > 0 is a system parameter. Since n ≥ 1, s is in (0, 1]. Atomic terms have the highest simplicity, 1.0 since their complexity is 1.

**Syntactic simplicity** is necessary when [Choice rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) is applied to selective question of the form "S => ?" or "? ==> P" and S and/or P are compound terms, the system strives to use the answer that has lowest syntactic simplicity since it will use less system resources to process.



