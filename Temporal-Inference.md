Temporal Inference is introduced in OpenNARS with [NAL 7](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) that introduces time into the statement.

## Event

All statements in OpenNARS are time dependent including the ones that are defined in "first order" inference. This happens because in most cases truth value of a statement is being changed during inference steps during some period of time and only rarely empirical statement holds its truth value for some time interval. As a result, system is able to describe temporal relations among different events. However for efficiency and implementation purposes, it is not possible and not always necessary taking the "time" attribution of a statement into consideration. Therefore events, as some type of a statement, are introduced into the system starting with NAL 7.

**An event** is a statement with a _time-dependent truth value_, that is, the evidential support summarized in its truth-value is valid only in its duration, which is a certain period of time between the moment the event starts and the moment it ends.

A usual Narsese statement can be viewed as an event with non-specified time interval except, that it includes current moment i.e. specifies the time.

## Time Representation

In OpenNARS, time is being represented indirectly using through events and their temporal relations. Ideally, an event can happen in some arbitrary time interval, during which inference rules can be defined on these time intervals, though, in NAL each event is represented by terms whose corresponding time interval might not be specified. Thus, OpenNARS always assumes less information and temporal order between two events E1 and E2 has been designed to fall in one of the following three categories:
1. E1 happens before E2
2. E1 happens after E2,
3. E1 and E2 happen at the same time.

The first two categories fall under same temporal relation and therefore, the primitive temporal relations are **“before-after”** and **“at-the-same-time”**.
**“before-after”** relation is irreflexive, antisymmetric, and transitive while **“at-the-same-time”** is irreflexive, antisymmetric, and transitive. Especially, adjectives like “past”, “current”, and “future” indicate temporal relations between events and “now”, taken as a special event.





