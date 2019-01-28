### Introduction

There are three types of sentences are defined in OpenNARS: judgment, question and goal. **Judgement** is the sentence with either predefined or derived truth value while **question** and **goal** are statements whose truth values has to be determined by the system. Goals and questions are similar in a way that both can contain [variables](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) however for the question, system evaluates truth value of the statement and unifies constant terms for the variables while for the goals system is asked to carry out some operation or sequence of operations to make a goal statement true thus achieving a desired goal. Therefore goal achievement is an example of [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) which itself employs [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference). Backward inference can be considered as an extension of forward inference and such all of the rules and truth functions remain the same. Below are descriptions of backward inference during [basic inference](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS) (questions)  and more complex procedural inference (goals)

### First order Backward Inference
The special case of Backward Inference is the [choice rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules), when it is applied to make a choice between two competing answers to a selective question. In general, backward inference rules for questions are determined in the following way: given two premises, question *Q* and judgement *J*, the system will try to rise a question *Q'* such that **answer for Q** can be derived from *J* and an answer for *Q'* using forward inference rules. 

Therefore having forward inference [Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) by rearranging the order of judgements and renaming the terms it is easy to see that the backward inference rules are identical. For example, from Syllogistic Rules table, renaming the conclusion C into question Q then judgement J2 into judgement J and judgement J1 as derived question Q' we will have identical rules as for forward inference, of course the truth functions are not used since derived question does not have truth value.

**Backward inference rule table**

Given two premises the left (J and Q), the derived question Q' is derived on the right (compare it with Syllogistic Rules table it is identical):
1. _Deduction_: {M → P <f1, c1>, S → M} |-- S → P
2. _Abduction_: {P → M <f1, c1>, S → M} |-- S → P
3. _Induction_: {M → P <f1, c1>, M → S} |-- S → P

This shows important property of triangularity that is always present in OpenNARS: for any three judgments J1, J2, and J3, if J3 can be derived from J1 and J2 by a syllogistic rule, then from J3 and J1 the system can generate J2', which has
the same statement as J2 however possibly with different truth values. In basic inference, if a question cannot be directly answered by the choice rule, backward inference is used to recursively search for derived questions until each of them has an answer, after which these answers will derive an answer to the original question using forward inference.

### Goals and Decision Making
A **goal** is a sentence containing an event that the system desires to realize.

