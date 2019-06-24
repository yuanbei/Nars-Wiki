A Narsese **sentence** can be one of the four types: Judgment, Question, Goal, and Quest.

**Judgement** is the most common type of sentence that consists of a statement with a truth-value attached. Formally, a judgment is a statement ended by "**.**" and followed by a truth-value. Example: **<raven --> [black]>. %1.0;0.9%**

**Question** is the type of sentence without truth-value attached and may contain variables. It asks the system to find or create a judgment as an answer. There are two types of questions: evaluative and selective. An evaluative question is of the form **Sta?** and the system should decide the truth-value for the statement **Sta**, whatever form it has. A selective question is on statement containing query variables, such as **<?x --> T>?** or **<T --> ?x>?** and the system is asked to come up with judgment where the [variable](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) _x_ is unified with some term. Questions are always finished with "**?**" at the end.

**Goal** is the type of sentence with an [event](https://github.com/opennars/opennars/wiki/Temporal-Inference) to be realized by the system by executing some operations. The attached desire value is the truth-value of the system's belief that the realization of the goal is desired.  Goals ask the system to carry out some operation in order to achieve the goal. A goal is formed as a statement followed by "!". 

**Quest** is a sentence that is similar to the question, however, while the question asks a truth-value, a quest asks a desire-value. Quests are finished with " ![equation](http://bit.ly/2S18QfZ) " at the end of a sentence.


