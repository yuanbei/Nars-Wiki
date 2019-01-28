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

### Goals and Decision Making in Procedural Inference
A **goal** is a sentence containing an event that the system desires to realize. Backward inference in procedural inference
is similar to the one discussed above. Given goal *G* and judgement *J*, if *J* provides direct solution to *G*, that is its truth value indicates that *G* has been achieved nothing is done (trivial case). Otherwise *G'* is derived such that *G* can be derived from *J* and *G'*. 

The backward inference in procedural inference corresponds to planning in a sense that for a goal G, group of **operations** is found to accomplish G. These **operations** are joined by "happens-before" and "happens-at-the-same-time" temporal *operators* defined in [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference). Thus planning is sequential selection of operations to achieve **desired** goal. If operations appears repeatedly such planning is learned and system acquires new skills.

System usually has multiple goals in memory, and it is important to decide which goal has the priority over the other. Furthermore, achieving one goal makes it more difficult to achieve the other, thus the system needs to know which goal is more desired. As discussed above, goals are sentences containing events then any event can become a goal during inference process some desire value is necessary to incorporate decision making mechanism. In OpenNARS "decision value" is a measurement to indicate the “degree of desire”, it is being attached to **every event sentence** since it might become a goal at a later stage. 

Desire value is something the system needs to find out by inference and in fact, desire-value of event S is the 
truth-value of the implication statement S ==> D, where D is a virtual statement describing the desired state of the system if a goal is achieved. Virtual statement D is a theoretical concept that never appears within the system in practice.
Given a goal G, its desire-value becomes the truth value of implication G ==> D. 

For example, if goal *G* has desire-value *V*, and the goal can be achieved by executing operation *O* (with truth value *T*), then we have two premises *G ==> D <V>* and *O ==> G <T>*. Using deduction we get *O ==> D <F deduction>* meaning  *O* becomes a derived goal, with a desire-value obtained by using the deduction truth function with *V* and *T* as arguments. After dropping the virtual statement D, we get a rule that derives a new goal *O* (with a utility value) from a
goal G (with a utility value) and a judgment  *O ==> G* (with a truth value). In case with multiple goals, if operation *O* will contribute to the achieving of goal *G1* but makes goal *G2* harder to achieve, the system will contains judgments *O ==> G1 <f1, c1>* and *O ==> G2 <f2, c2>*, where *f1* is close to 1, and f2 is near 0. When both *G1* and *G2* are both desired the system will get two *O ==> D* that is, the goal A gets two utility values, obtained from different sources and should be merged using the [revision rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules).

The decision-making rule will turn candidate goals with high desirevalue and plausibility into goals being actually pursued by the system.
Definition 12.5. The plausibility of candidate goal G is the truth-value of
the answer to question \? =) G" where the query variable ‘?’ is instantiated
by an executable operation.
1Please note that NARS does not self-program by changing its own source code, which
remains unchanged at a lower level.August 8, 2012 16:25 World Scientific Book - 9in x 6in NAL-Wang
NAL-8: Operations and Goals as Events 153
Intuitively speaking, the plausibility of G is the truth-value of \There is a
way to achieve G".
As mentioned previously, the system’s procedural knowledge often has
the form of \(condition; operation) =) consequence". From such a piece
of knowledge and a belief about the condition, the truth-value of statement
\operation =) consequence" can be decided, which provide a candidate
answer for the question \? =) consequence". When more than one such
candidate exists, the choice rule will pick one that has high expectation and
low complexity. This answer is the one that provides the plausibility of
event consequence.
Decision-making Rule. A candidate goal is actually pursued by the system, when its expected desirability d and expected plausibility p satisfy
condition p(d − 0:5) > t, where t is a positive constant.
When 0.5 is added to both sides of the formula, the above \decisionmaking function" has the same form as the expectation function defined in
Table 4.2, with desirability as frequency and plausibility as confidence. Here
the \expected desirability" and \expected plausibility" are the output of the
expectation function with the desirability and the plausibility of the goal
as input, respectively. The threshold t is another \personality parameter"
of the system, and measures the system’s cautiousness.
The above rule can be compared with the Maximum Expected Utility
Principle of decision theory, which asks the system to always choose the
alternative that has the largest expected utility value [Savage (1954)]. The
NAL decision-making rule is built according to the same intuition, where
the expected desirability is similar to the utility of an event, while the expected plausibility is similar to its probability. However, their difference is
that: