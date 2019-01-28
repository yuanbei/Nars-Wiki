### Introduction

There are three types of sentences are defined in OpenNARS: judgment, question and goal. **Judgement** is the sentence with either predefined or derived truth value while **question** and **goal** are statements whose truth values has to be determined by the system. Goals and questions are similar in a way that both can contain [variables](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) however for the question, system evaluates truth value of the statement and unifies constant terms for the variables while for the goals system is asked to carry out some operation or sequence of operations to make a goal statement true thus achieving a desired goal. Therefore goal achievement is an example of [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) which itself employs [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference). Backward inference can be considered as an extension of forward inference and such all of the rules and truth functions remain the same. Below are descriptions of backward inference during [basic inference](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS) (questions)  and more complex procedural inference (goals)

### First order Backward Inference
The special case of Backward Inference is the [choice rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules), when it is applied to make a choice between two competing answers to a selective question. In general, backward inference rules for questions are determined in the following way: Given two premises, question *Q* and judgement *J*, the system will try to rise a question *Q'* such that **answer for Q** can be derived from *J* and an answer for *Q'*.

### Goals and Decision Making
A **goal** is a sentence containing an event that the system desires to realize.

