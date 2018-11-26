Temporal Inference is introduced in OpenNARS with [NAL 7](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) that introduces time into the statement.

## Event

All statements in OpenNARS are time dependent including the ones that are defined in "first order" inference. This happens because in most cases truth value of a statement is being changed during inference steps during some period of time and only rarely empirical statement holds its truth value for some time interval. As a result, system is able to describe temporal relations among different events. However for efficiency and implementation purposes, it is not possible and not always necessary taking the "time" attribution of a statement into consideration. NAL 7 introduces events, as some type of a statement, but events is not defined as a Narsese grammatical category, it just refers to statements that have temporal information associated.

**An event** is a statement with a _time-dependent truth value_, that is, the evidential support summarized in its truth-value is valid only in its duration, which is a certain period of time from the moment the event starts to the moment it ends.

Thus, event is a statement whose truth-value may change, and this is different from the changes caused by the accumulation of evidence. During specified time period of an event, the evidence collected before becomes outdated, and should be discarded when the current situation is under consideration.

## Time Representation

In OpenNARS, time is being represented indirectly through events and their temporal relations. Ideally, an event can happen in some arbitrary time interval, during which inference rules can be defined on these time intervals, though, in NAL each event is represented by terms whose corresponding time interval might not be specified. Thus, OpenNARS always assumes less information. Time interval of truth-value can be seen as a point, and referred to as when the corresponding event "happens", then the temporal relation between two atomic events E1 and E2 has been designed to fall in one of the following three categories:

1. E1 happens before E2
2. E1 happens after E2,
3. E1 and E2 happen at the same time.

The first two categories fall under same temporal relation and therefore, there are **two** primitive temporal relations: **“before”** and **“when”**. **“before”** relation is irreflexive, antisymmetric, and transitive while **“when”** is reflexive, symmetric, and transitive. 

These two temporal relations are represented using “ordinary relations” defined in NAL-4. Also NAL-7 introduces duration relation, that is if “(t1 × t2) → duration” and “(t1 × t2)” and event E happen at the same time, then E lasts for the duration of a time period from t1 to t2.

In OpenNARS terms t1 and t2 are events themselves with omitted durations and not accurate measurement of absolute time.
If an absolute time is used to represent the temporal property of event E, then that time itself is to be treated as a special event T, and these two events, E and T, are described as happening at the same time.





