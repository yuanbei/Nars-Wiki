Compound Terms, Set Operations and **compositional rules** are introduced in NAL-3 and briefly mentioned on [NAL page](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) however since it is one of the major aspect of reasoning in OpenNARS they are described here in more detail.

Before rules are established themselfs Compound terms needed to be specified, basically compouind terms are term that consists from multiple components or formally: <br/> _A compound term (con C1,...,Cn) is a term formed by a term connector, con, that **connects** one or more terms that are called the components of the compound._ <br/>The order of the components does matter, and the components are allowed to be same. Term connector is a logical constant with no internal structure and connectors are predefined as part of NALs. 

Since compound terms may have compound within themselves some hierarchy has been established: Each term has syntactic complexity an integer number. The syntactic complexity of an atomic term is 1. The syntactic complexity of a compound term is 1 plus the sum of the syntactic complexities of its components. 
Thus, the syntactic complexity of a compound term is just the number of  words and connectors within its structure, and of course the process is recursive. 



