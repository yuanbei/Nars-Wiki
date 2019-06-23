In NARS a **term** refers to a concept within the system, as a part of a [sentence](https://github.com/opennars/opennars/wiki/Sentence:-types,-format) that expresses the relation between some concepts. 

Consider a sentence (discussed below) "Ravens are black", in [Narsese](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)) it can be represented as <br/><br/>**<raven --> [black]>.%1.0;0.9%**<br/><br/>
Now both "raven" and "[black]" are terms that in this particular case along with inheritence [copula](https://github.com/opennars/opennars/wiki/Narsese-symbol-list-(ASCII-version-)) create a statement. The statement  plus the punctiation and truth-value form a **judgment**, which is a type of [sentence](https://github.com/opennars/opennars/wiki/Sentence:-types,-format). In more complex Narsese sentences, terms may be statements themselves. For example, consider sentence "John knows that whale is a kind of mammal" that is <br/><br/>**<(*, {John}, {<whale --> mammal>}) --> knows>. %1.0;0.9%**<br/><br/> Here term "<whale --> mammal>" is a statement itself that consists of simpler terms "whale" and "mammal" which all are part of a sentence. 

In the above example, a term can be one of three types: atomic, compound, and statement (which is a special type of compound term). All three types of terms can have relations with each other. 

An **atomic** term is just a word as in the first example, it is a unique identifier with no internal structure. 

A **compound** term is more complex. It is formed by a _connector_ from one or more terms, called its _components_. The order of components usually matters. In the second example there is a compound term **(\*, {John},{<whale --> mammal>})** here it consists of two components "{John}" and "{<whale --> mammal>}" connected by the _product_ connector "*". All connectors are listed in the [grammar of Narsese](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)).

**Term as a Statement** is a term that is a statement itself and is part of a bigger sentence with truth value. "term as a statement" has meaning only but no truth value, it is part of a sentence with truth value. As in the second example   <whale --> mammal> is "term as a statement", it only states that "whale is mammal" but no truth value is attached to it, however, the truth value is attached to the entire sentence. 

**Syntactic Complexity**: for each term system maintains syntactic complexity. If a term is atomic its syntactic complexity is 1. If term is compound, then its syntactic complexity is one bigger than the highest syntactic complexity of its components.

For more clarification see types of [sentences](https://github.com/opennars/opennars/wiki/Sentence:-types,-format)