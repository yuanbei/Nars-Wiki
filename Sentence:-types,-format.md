On this page only sentences are discussed as a complete structural derivations that consist of terms.  Do not mix them with "term as a statement" discussed on [term](https://github.com/opennars/opennars/wiki/Term:-types,-format) page and do not mix sentence with statement. Statement has only meaning with no truth value attached but sentence is a statement with truth or desire value with only exception to Question type sentences.

**Sentence** can be one of the four types: Judgment, Question, Goal and Quest. Sentence in Narsese is enclosed within "<" and ">" symbols and except for Questions must have pair of rational numbers attached which is either [truth-value](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) or [desire-value](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples)

**Judgement** is the most common type of sentence that consists of two or more terms of any type and has truth value attached. Judgement statement is always finished with "." and followed by truth vale. Example: **<raven --> [black]>. %1.0;0.9%**

**Question** is the type of sentence without truth value attached and may contain variables. It asks the system to come up with truth value or judgement. There are two types of questions: evaluative and selective. Evaluative question is of the form **<S -->T>?** and the system should come with the truth value. Selective question is of the form **<?x --> T>?** or **<T --> ?x>?** and system is asked to come up with judgement where [variable](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) _x_ is unified with some term. Questions are always finished with "?" at the end of a sentence

**Goal** sentence is a statement containing an [event](https://github.com/opennars/opennars/wiki/Temporal-Inference) and attached desire value that looks identical to truth value but has different semantics. Goals asks the system to carry out some operation in order to achieve the goal. Let A be some operation to achieve goal G, then system is asked to come up with sentence <A ==> G> %f;c% whose truth value is as as close to 1 as possible. Goals are finished with "!" at the end of a sentence. 

**Quest** is a sentence that is similar to the question, however while the question asks to come up with some truth value, quest is about desire value of an event. Goals are finished with ![equation](http://bit.ly/2S18QfZ) at the end of a sentence.


