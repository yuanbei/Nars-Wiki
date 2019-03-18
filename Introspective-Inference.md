The information present here is closely related to [Emotion and Internal experience](https://github.com/opennars/opennars/wiki/Emotion-and-Internal-experience). Feel free to read it along with this page. 

## Introspective Inference
Introspective Inference will be mainly implemented as a set of mental operations whose major consequences are within the system itself. These operations carries out various types of self-monitoring and self-control.

## Deliberate control
The package nars.operator.mental contains operators that allow the system to deliberately override the automatic inference control mechanism:

* task creation: This group of operators each takes a Term as argument, and uses it as content to create a new task to be processed: ^believe for judgment, ^want for goal, ^wonder for question, and ^evaluate for query.

* truth-value/desire-value correction: The operators ^doubt and ^hesitate each takes a Term as argument, find the corresponding Concept, then reduce the confidence by Parameters.DISCOUNT_RATE of all the truth-values and desire-values, respectively. These operations are used when the system realized that some previous evidence is unreliable or unjustified. Please note that no operator is needed to increase the confidence value, because it can be achieved by the revision rule with new evidence.

* compound compiling: The operators ^name and ^abbreviate both builds a similarity relation with high confidence between a compound term and an atomic term, so as to reduce the syntactic complexity of the corresponding concept. Their difference is that ^name takes a given atomic term as the second argument, while ^abbreviate makes a new internal name.

* concept activation: The operators ^remind increases the priority of a specified concept; ^consider directly carries out an inference cycle on a specified concept.

* operator binding: The operators ^register add a new operator when the system is running.

The name of a mental operator only roughly corresponds to its meaning. The exact meaning of an operator is revealed by its preconditions and consequences.

These mental operators are introduced for experimental purpose. The details in each of them may be revised, and other operators may be introduced. In general, each operator should be relatively simple and meaningful. It is neither necessary nor possible for the system to explicitly manage all its internal actions, so it is not a good idea to define a large number of mental operators.
