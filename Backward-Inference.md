### Introduction

There are four types of sentences are defined in [Narsese](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)): judgment, goal, question, and query, though sometimes query is considered as a type of question. Among the four, only a judgment contains a truth-value.

In a typical inference step of NARS, a task and a belief are used as premises by an inference rule, and a conclusion is a set of derived tasks. The tasks in the premise and conclusion contain sentences of the same type, which can be any one of the above four types. On the other hand, a belief is always a judgment. Therefore, the inference in a step belongs to one of the two categories:
* **Forward inference**, which takes two judgments as premises, and derives one or more judgments as conclusions, and the truth-value of each conclusion is calculated by a corresponding truth-value function. The rules described in the other Wiki pages on inference rules all belong to this category.
* **Backward inference**, which takes one judgment (the belief) and a non-judgment (goal/question/query, the task) as premises, and derives one or more tasks of the same type, and the conclusions have no truth-value (though goals will have desire-value).

The backward inference in NARS has no specific rules. Instead, it uses the (forward) inference rules _backwards_. That is, for each forward rule _{B, T} |- T'_, there is a backward rule _{B, T'} |- T_, where the two rules use the same belief, and exchange sentences in the given task and the derived task. In this way, backward inference carries out goal and question (query) derivation, according to the meta-rule that task _T'_ is derived from task _T_ and belief _B_, if and only if its solution can derive a solution of _T_ with _B_.

In this way, if a goal/question/query cannot be directly answered/satisfied by a belief using the choice rule, backward inference will generate its derived tasks recursively. When such a derived task is resolved, its solution will trigger the "backtracking" forward inference to eventually contribute to the solution or the original task.

### Backward Syllogistic Inference

As a special case of backward inference, the (forward) [Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) can be turned backward by rearranging the order of judgments and renaming the terms, and it turns out that the inference rules look the same as the forward version if the truth-value function is omitted:
* {M --> P <f, c>, S --> M} |- S --> P
* {P --> M <f, c>, S --> M} |- S --> P
* {M --> P <f, c>, M --> S} |- S --> P
* {P --> M <f, c>, M --> S} |- S --> P

Therefore, for syllogistic rules, the forward and backward inference share the same code by which the content of the conclusion is structured. The difference is only in the type of the derived task and the optional truth-value (desire-value) calculation.

### Planning and skill acquisition

A **goal** is a sentence containing an event that the system desires to realize, as described in [Procedural Inference](https://github.com/opennars/opennars/wiki/Procedural-Inference). Backward inference in procedural inference is similar to the one discussed above. Given goal *G* and judgment *J*, if *J* provides a direct solution to *G*, that is its truth-value indicates that *G* has been achieved, then nothing is needed to be done (trivial case). Otherwise *G'* is derived such that *G* can be derived from *J* and *G'*. 

The backward inference in procedural inference corresponds to planning in a sense that for a goal G, group of operations is found to accomplish G. These operations are joined by the connectors to form compound operations, as described in [Procedural Inference](https://github.com/opennars/opennars/wiki/Procedural-Inference). If the same goal appears repeatedly, the corresponding plan is remembered, and the system acquires a new skill.
