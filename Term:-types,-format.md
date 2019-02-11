In OpenNARS and Narsese grammar **term** is a part of a sentence that appear at any side of a copula (connector). 

Consider a judgment statement (discussed below) "raven is black", in [Narsese](https://github.com/opennars/opennars/wiki/Input-Output-Format) it will look as <br/><br/>**<raven --> [black]>.%1.0;0.9%**<br/><br/>
Now both "raven" and "[black]" are terms that in this particular case along with inheritence [copula](https://github.com/opennars/opennars/wiki/Narsese-symbol-list-(ASCII-version-)) create a judgment statement. In a more complex Narsese statements, terms may be statements themselves for example consider statement "John knows that whale is a kind of mammal" that is <br/><br/>**<*({John},<whale --> mammal>) ==> knows>. %1.0;0.9%**<br/><br/> Here term "<whale --> mammal>" is a sentence itself that is part of a bigger statement. 

Term can be one of three types: atomic, compound and "term as a sentence". All three types of terms can have relations between each other. 

**Atomic** term is just a word as in the first example, it is unique identifier with no internal structure. 

**Compound** terms are more complex. They are terms formed by one or more terms, called its components with an operator. The order of components usually matters. In the second example there is a compound term **\*({John},<whale --> mammal>)** here it consists of two components "{John}" and "<whale --> mammal>" connected by product operator "*"

**Term as a Sentence** is a term that is a sentence itself and is part of a bigger sentence with truth value. "term as a sentence" itself has meaning only but no truth value, it is part of a bigger statement with truth value. As in the second example   <whale --> mammal> is "term as a sentence", it only states that "whale is mammal" but no truth value is attached to it, however the truth value is attached to the entire statement. 

**Syntactic Complexity**: for each term system maintains syntactic complexity.If a term is atomic its syntactic complexity is 1. If term is compound, then its syntactic complexity is one bigger than the highest syntactic complexity of its components.

For more clarification see types of [sentences](https://github.com/opennars/opennars/wiki/Sentence:-types,-format)