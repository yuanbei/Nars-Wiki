> ### OpenNarsOneDotSix  
> Functions and remaining issues of Open-NARS 1.6.x.

***
### Introduction

Open-NARS 1.6.x is different from 1.5.x in the following major aspects:

In logic, it implements NAL-7, NAL-8, and NAL-9, and therefore completely implements NAL, as specified in Non-Axiomatic Logic: A Model of Intelligent Reasoning.
It introduces some new ideas to be further explored, such as PerceptionInNARS and Plugins.
In control, it refines the automatic resources allocation that has been there from the beginning, and combines it with the voluntary control introduced in NAL-9.
In software structure, it absorbs the ideas from previous discussions, as well as the recent discussions. The program has a completely new GUI and very different internal structure.

***
### Temporal Inference (NAL-7)

#### Representation of temporal information

Beside Non-Axiomatic Logic: A Model of Intelligent Reasoning, temporal reasoning in NARS is also discussed in Issues in Temporal and Causal Inference. A previous implementation exists as version 1.3.3, with working examples.

Beside using terms whose meanings are explicitly temporal, Narsese is extended to allow temporal order among components in certain CompoundTerm, as well as an "occurrence time stamp" on a truth-value.

In package nars.language, the following three classes representing compound terms will be given an optional temporal order among its components: Implication, Equivalence, and Conjunction. This order can be represented either as subclasses, or as an attribute that takes three possible values: -1 for backward, +1 for forward, 0 for concurrent, and 2 for "no temporal order". These numbers are selected to make the later processing easy and natural, so should not be changed unless after careful consideration. The plain text forms of the term connectors are listed in InputOutputFormat.

In class nars.entity.Stamp, an occurrenceTime records the (observed, remembered, or estimated) occurrence time of the event, together with its creation time. Different from the description in the book, the "tense" of a sentence is not stored with a sentence, but is only used at the interface. When a sentence is an input or output, the internal occurrenceTime will be translated to/from the external sense that is explicitly expressed in Narsese, as listed in InputOutputFormat.

A system parameter DURATION is used to define the "present tense" as for events with an occurrenceTime in the [-DURATION, DURATION] neighborhood of the current time, as given by the system's internal clock. It's current default value is 5. The previous idea is to take 1 as its value, so "presently" means the current working cycle, but it seems too restrictive. For an input judgment, if its tense is "present", its occurrenceTime will be set to the current time on the internal clock, "past" is mapped to "current time - DURATION", and "future" to "current time + DURATION". If no tense is used, the occurrenceTime takes a special value ETERNAL. The reverse mapping is used for output.

####Inference on temporal order

As explained in the publications, temporal inference in NARS is designed by processing the logical and the temporal aspects separately. Therefore all the existing rules will be kept, except that the conclusion may contain a temporal term (with temporal order among components), a time interval (similar to the numbers in experience), and/or a temporal truth-value (with an occurrence time).

The temporal order in CompoundTerms is processed in the following way:

1. As described in the book, each inference rule of NAL-6 is extended by using the temporal copulas and connectors to replace the atemporal ones in the premises, then identifying the conclusions where both the logical and the temporal relations can be derived, so as to establish valid inference rules for NAL-7.

2. Different from what is hinted in the book, the temporal order is taken to be binary, not multi-valued, so the matter of degree in the truth-value is completely caused by the logical factor, not the temporal factor. For this reason, in all inference rules (both strong and weak), the temporal order among the terms in the conclusion is the same order as those terms in the premises. If no such a temporal order can be decided in a certain combination of the terms, no conclusion is derived.

#####-Inference on occurrence time
In most rules, the occurrenceTime is processed independent of the other aspects of the rule. There are the following cases:

* If both premises are ETERNAL, so is the conclusion. Therefore all the inference rules defined in the lower layers remain valid.
* If the task is "tensed" (i.e., with an occurrenceTime that is not ETERNAL) but the belief is not, then the conclusion has the same occurrenceTime as the tensed premise.
* If the task is not tensed but the belief is, then an eternalization rule is used to take the belief as providing evidence for the sentence in the task.
* If both premises are tensed, then the belief is "projected" to the occurrenceTime of the task. Ideally, temporal inference is valid only when the premises are about the same moment, i.e., have the same occurrenceTime or no occurrenceTime (i.e., eternal). However, since occurrenceTime is an approximation and the system is adaptive, a conclusion about one moment (that of the belief) can be projected to another (that of the task), at the cost of a confidence discount. Let t0 be the current time, and t1 and t2 are the occurrenceTime of the premises, then the discount factor is d = 1 - |t1-t2| / (|t0-t1| + |t0-t2|), which is in [0,1]. This factor d is multiplied to the confidence of a promise as a "temporal discount" to project it to the occurrence of the other promise, so as to derive a conclusion about that moment. In this way, if there are conflicting conclusions, the temporally closer one will be preferred by the choice rule.
Normally, if the premises are "tensed", so is the conclusion --- the knowledge derived about a moment is only valid for that moment. It is through "eternalization" that an eternal conclusion is arrived, at the cost of a confidence lost.

In principle, all inference rules should take temporal information into account. However, since an inference rule may be implemented as the cooperation of multiple methods, not all of them will be responsible to check temporal information.

#####-Temporal induction and detachment
An inference where temporal order and occurrence time are tangled is temporal induction and its reverse, detachment (as special case of deduction and abduction).

In NARS, temporal induction refers to the situation where events e1 and e2 are observed as occurring in succession, with a time interval in between with a length of n clock cycles. As far as this sequence of events is noticed by the system, an inductive conclusion (&/,e1,interval(n)) =/> e2 is derived.

This rule is one of the exceptions of the "generalized syllogistic" pattern in NAL inference rules, which requires the premises to have a common term. This pattern guarantees the semantic relevance among the statements involved, and also greatly reduced the number of legal combinations of premises. The current exception is allowed, because the two events are related temporally, though not semantically, and in future works on sensation organs similar exceptions will be allowed for spatially related events to be combined into compound events without shared components. This rule also includes variable introduction. If e1 and e2 have common subject or predicate, an independent variable will be introduced in the conclusion.

**Issue:** There may be other forms of variable introduction where the shared term is neither the common subject nor the common predicate.

**Issue:** Whether to derive conclusions like e2 =\> (&/,e1,interval(n))?

**Issue:** Though in principle temporal induction can happen between any two tensed judgments, to do that exhaustively is not affordable. Beside what has been implemented, the rule may be invoked (1) as question driven, too, in response to e1 =/> e2? or similar questions, and (2) exhaustively between events in a buffer (the system's "flow of consciousness") that contains "active events", which is separated from the current task buffers in that it only contains significant events after preprocessing. In this way, non-event tasks and trivial (i.e., anticipated or irrelevant) events will not be involved.

As for the time interval n between the two events, to simply derive e1 =/> e2 is correct, but it does not capture the temporal information about the interval. To use another event to represent the interval (as tried in version 1.3.3) is too accurate to be useful, because (&/,e1,interval(100)) =/> e2 and (&/,e1,interval(101)) =/> e2 probably should be merged by the revision rule, since the difference between the two numbers are negligible. For this consideration, in the current implementation, the interval is represented by a special type of term, which approximately record m = log(n) as an integer. With such a belief as premise, the detachment rule will do deduction with e1, and abduction with e2, and the occurrenceTime of the conclusion is calculated from that of the other event, plus or minus exp(m) to approximately recover the n value. Whether the log/exp functions should be replaced by power functions (such as sqrt/square) is a question to be answered later. As in other places, whenever an accurate time interval is needed, it is always possible to replace the approximate time interval by a better defined event, so that is not an issue.

Since the interval measurement is subjective, it will not appear in the system's communication language, but is used in internal representation only. In the future, different intervals will be associated with different temporal terms, such as "after a while", "hours later", etc., via learning, so as to be expressible in communication.