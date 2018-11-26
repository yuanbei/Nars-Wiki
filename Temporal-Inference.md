Temporal Inference is introduced in OpenNARS with [NAL 7](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) that introduces time into the statement.

## Event

All statements in OpenNARS are time dependent including the ones that are defined in "first order" inference. This happens because in most cases truth value of a statement is being changed during inference steps during some period of time and only rarely empirical statement holds its truth value for some time interval. As a result, system is able to describe temporal relations among different events. However for efficiency and implementation purposes, it is not possible and not always necessary taking the "time" attribution of a statement into consideration. NAL 7 introduces events, as some type of a statement, but events is not defined as a Narsese grammatical category, it just refers to statements that have temporal information associated.

**An event** is a statement with a _time-dependent truth value_, that is, the evidential support summarized in its truth-value is valid only in its duration, which is a certain period of time from the moment the event starts to the moment it ends.

Thus, event is a statement whose truth-value may change, and this is different from the changes caused by the accumulation of evidence. During specified time period of an event, the evidence collected before becomes outdated, and should be discarded when the current situation is under consideration.

## Temporal Relations

In OpenNARS, time is being represented indirectly through events and their temporal relations. Ideally, an event can happen in some arbitrary time interval, during which inference rules can be defined on these time intervals, though, in NAL each event is represented by terms whose corresponding time interval might not be specified. Thus, OpenNARS always assumes less information. Time interval of truth-value can be seen as a point, and referred to as when the corresponding event "happens", then the temporal relation between two atomic events E1 and E2 has been designed to fall in one of the following three categories:

1. E1 happens before E2
2. E1 happens after E2,
3. E1 and E2 happen at the same time.

The first two categories fall under same temporal relation and therefore, there are **two** primitive temporal relations: **“before”** and **“when”**. **“before”** relation is irreflexive, antisymmetric, and transitive while **“when”** is reflexive, symmetric, and transitive. 

These two temporal relations are represented using “ordinary relations” defined in NAL-4. Also NAL-7 introduces duration relation, that is if “(t1 × t2) → duration” and “(t1 × t2)” and event E happen at the same time, then E lasts for the duration of a time period from t1 to t2.

In OpenNARS terms t1 and t2 are events themselves with omitted durations and not accurate measurement of absolute time.
If an absolute time is used to represent the temporal property of event E, then that time itself is to be treated as a special event T, and these two events, E and T, are described as happening at the same time.


## Time Representation

In OpenNARS, there is no sharp boundary of time interval that specified in event, or even time interval is not well-defined, for every event. However being a real-time system, OpenNARS not only needs to reason about time, but also reason in time, which demands a personal time monitoring mechanism. The time is then measured by the system’s internal "clock" defined by its own working cycle.

Some temporal properties of an event in OpenNARS is specified with respect to the events defined by an internal clock, with the system’s inference cycle as a unit. It is possible for the internal activity to take a constant time, which
can be achieved by the current design however that since time is measured through system's working inference cycle, time measurement is relevant to unique system only, that is different instances of OpenNARS will have different "time" to an event in their common environment. 

The real-time experience of a OpenNARS is a sequence of Narsese sentences, separated by non-negative numbers indicating the interval in inference cycles between the arriving time of subsequent sentences. That is, let Si be Narsese sentences and Ni be non-negative integers, a real-time experience is expressed as string S1; N1; S2; N2; S3; N3;
which means that sentence S1 is received at a certain moment, then, after N1 inference cycles, S2 is received etc. Special case when N = 0, two surrounding events are accepted at the same moment in time.

## Temporal Copulas

It is natural for second temporal relations "when", to represent Events E1 and E2 that happen in the same moment of time using and "∧" operator. Therefore, temporal relations are treated a as a variants of statement operator plus temporal information. Then statement operator “conjunction” (“,”) represents “sequential conjunction” ("before" temopral relation) and (“;”) represents “parallel conjunction” ("when" temporal relation). For example, “(E1, E2)” means “E1 occurs before E2”, while “(E1; E2)” means E1 and E2 "happen at the same time". 

There are also the temporal variants of implication and equivalence defined in NAL-5. For an implication statement <S ⇒ T> where S and T are events, three different temporal relations are established:

1. **<S /⇒ T>** means S happens before T , the statement is called “predictive implication”, where S is called a sufficient precondition of T, and T a necessary postcondition of S.

2. **<S \⇒ T>** means S happens after T, the statement is called “retrospective implication”, where S is called a sufficient postcondition of T, and T a necessary precondition of S.

3. **<S |⇒ T>** means S happens at the same time as T, the statement is called “concurrent implication”, where S is called a sufficient co-condition of T, and T a necessary co-condition of S.

There are three types of temporal equivalence relations (predictive, retrospective, and concurrent) that are defined in a similar way: <S /⇔ T>, <T \⇔ S> and <S |⇔ T>. Narsese only represent <S /⇔ T> and <S |⇔ T> s only represented as
“S /⇔ T ”, so the copula “ \⇔” is in the grammar of NAL-7. 

Important to note, for judgments about the same statement with the same timestamp, [revision rule](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) is still used to revise truth value. For judgments about the same statement with different time stamps, revision rule is not applicable instead these judgments are used to describe changes in the environment. 

