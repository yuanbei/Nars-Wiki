### Introduction

There are three types of sentences are defined in OpenNARS: judgment, question and goal. **Judgement** is the sentence with either predefined or derived truth value while **question** and **goal** are statements whose truth values has to be determined by the system. Goals and questions are similar in a way that both can contain [variables](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) however for the question, system evaluates truth value of the statement and unifies constant terms for the variables while for the goals system is asked to carry out some operation or sequence of operations to make a goal statement true thus achieving a desired goal. Therefore goal achievement is an example of [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) which itself employs [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference). Backward inference can be considered as an extension of forward inference and such all of the rules and truth functions remain the same. Below are descriptions of backward inference during [basic inference](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS) (questions)  and more complex procedural inference (goals)

### First order Backward Inference
The special case of Backward Inference is the [choice rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules), when it is applied to make a choice between two competing answers to a selective question. In general, backward inference rules for questions are determined in the following way: Given two premises, question *Q* and judgement *J*, the system will try to rise a question *Q'* such that **answer for Q** can be derived from *J* and an answer for *Q'* using forward inference rules. Therefore having forward inference [Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) by rearranging the order of judgement and renaming the term it is easy to see that the backward inference rules are identical. For example rename the conclusion C into question Q then judgement J2 into judgement J and judgement J1 as derived question Q' we will have identical rules as for forward inference, of course the truth functions are not used since derived question does not have truth value.

Defined in this way, it is easy to get backward inference rules from
forward inference rules. For example, for a given forward-inference rule
table, first we take the conclusions in the table as questions (Q), one premise
(J2) as a judgment (J), and the other premise (J1, without truth value) as
the derived question. After renaming the terms and rearranging the order,
we get a backward-inference rule table, in which some terms in the questions
can be a “??”, indicating a query for terms satisfying given condition.
For syllogistic rules on the “→” relation (i.e., deduction, abduction, induction, and exemplification), the backward-inference table is the following:
Q \ J M → P P → M
S → M S → P S → P
M → S S → P S → P
This table turns out to be identical to the syllogism table introduced previously, if we ignore the truth-value functions. This elegant symmetry reveals
an implicit property of the syllogistic rules of NARS — that is, for any three
judgments J1, J2, and J3, if J3 can be derived from J1 and J2 by a syllogistic rule, then from J3 and J1 the system can generate J20, which has
the same statement as J2 (the truth values of J2 and J20 may be different).
Intuitively, the three inheritance relations constitute a triangle from any
two sides of which the third side can be derived. Such a property does
not give rise to infinite loops in the system, because if J3 is really derived
from J1 and J2, it must share “serial numbers” with each of the two, which
prevents the system from taking J3 and J1 (or J2) as premises in further
inferences.
79In NAL-1, if a question cannot be directly answered by the choice rule,
backward inference is used to recursively“reduce” the question into derived
questions, until all of them have direct answers. Then these answers, together with the knowledge contributed in the previous backward inference,
will derive an answer to the original question by forward inference.




### Goals and Decision Making
A **goal** is a sentence containing an event that the system desires to realize.

