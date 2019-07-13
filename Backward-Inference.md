### Introduction

There are four types of sentences are defined in [Narsese](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)): judgment, goal, question, and query, though sometimes query is considered as a type of question. Among the four, only a judgment contains a truth-value.

In a typical inference step of NARS, a task and a belief are used as premises by an inference rule, and a conclusion is a set of derived tasks. The tasks in the premise and conclusion contain sentences of the same type, which can be any one of the above four types. On the other hand, a belief is always a judgment. Therefore, the inference in a step belongs to one of the two categories:
* **Forward inference**, which takes two judgments as premises, and derives one or more judgments as conclusions, and the truth-value of each conclusion is calculated by a corresponding truth-value function. The rules described in the other Wiki pages on inference rules all belong to this category.
* **Backward inference**, which takes one judgment (the belief) and a non-judgment (goal/question/query, the task) as premises, and derives one or more tasks of the same type, and the conclusions have no truth-value (though goals will have desire-value).

The backward inference in NARS has no specific rules. Instead, it uses the (forward) inference rules _backwards_. That is, for each forward rule _{B, T} |- T'_, there is a backward rule _{B, T'} |- T_, where the two rules use the same belief, and exchange sentences in the given task and the derived task. In this way, backward inference carries out goal and question (query) derivation, according to the meta-rule that task _T'_ is derived from task _T_ and belief _B_, if and only if its solution can derive a solution of _T_ with _B_.

### Backward Syllogistic Inference

As a special case of backward inference, the (forward) [Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) can be turned backward by rearranging the order of judgments and renaming the terms, and it turns out that the inference rules look the same as the forward version if the truth-value function is omitted:
* {M --> P <f, c>, S --> M} |- S --> P
* {P --> M <f, c>, S --> M} |- S --> P
* {M --> P <f, c>, M --> S} |- S --> P
* {P --> M <f, c>, M --> S} |- S --> P

Therefore, for syllogistic rules, the forward and backward inference share the same code by which the content of the conclusion is structured. The difference is only in the type of the derived task and the optional truth-value (desire-value) calculation.

### Goals and Decision Making in Procedural Inference
A **goal** is a sentence containing an event that the system desires to realize. Backward inference in procedural inference
is similar to the one discussed above. Given goal *G* and judgement *J*, if *J* provides direct solution to *G*, that is its truth value indicates that *G* has been achieved nothing is done (trivial case). Otherwise *G'* is derived such that *G* can be derived from *J* and *G'*. 

The backward inference in procedural inference corresponds to planning in a sense that for a goal G, group of **operations** is found to accomplish G. These **operations** are joined by "happens-before" and "happens-at-the-same-time" temporal *operators* defined in [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference). Thus planning is sequential selection of operations to achieve **desired** goal. If operations appears repeatedly such planning is learned and system acquires new skills.

System usually has multiple goals in memory, and it is important to decide which goal has the priority over the other. Furthermore, achieving one goal often makes more difficult to achieve the other, thus the system needs to know which goal is more desired. As discussed above, goals are sentences containing events, then any event can become a goal during inference process and therefore some desire value is necessary to incorporate decision making mechanism. In OpenNARS "desire value" is a measurement to indicate the “degree of desire”, it is being attached to **every event sentence** since any event might become a goal at a later time. 

Desire value is something the system needs to find out by inference and in fact, desire-value of event S is the 
truth-value of the implication statement S ==> D, where D is a virtual statement describing the state of the system if a goal is achieved. Virtual statement D is a theoretical concept that never appears within the system in practice.
Given a goal G, its desire-value becomes the truth value of implication G ==> D. 

For example, if goal *G* has desire-value *V*, and the goal can be achieved by executing operation *O* (with truth value *T*), then we have two premises *G ==> D <V>* and *O ==> G <T>*. Using deduction we get *O ==> D <F deduction>* meaning  *O* becomes a derived goal, with a desire-value obtained by using the deduction truth function with *V* and *T* as arguments. After dropping the virtual statement D, we get a rule that derives a new goal *O* (with a utility value) from a goal G (with a utility value) and a judgment  *O ==> G* (with a truth value). 

In case with multiple goals, if operation *O* will contribute to the achieving of goal *G1* but will make goal *G2* harder to achieve, the system will contain judgments *O ==> G1 <f1, c1>* and *O ==> G2 <f2, c2>*, where *f1* is close to 1, and f2 is near 0. When both *G1* and *G2* are desired the system will get two *O ==> D* that is, the goal *O* gets two utility values, obtained from different sources and should be merged using the [revision rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules). The final decision of choosing an operation is made when the expectation of the desire-value of the goal is above a certain threshold, which is a pre-defined system parameter. That is, the system only pursues goals whose overall expected desirability is sufficiently high.