Temporal Inference is introduced in [NAL-7](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-the-logic-behind-OpenNARS) where time is directly represented and processed.

## Event

The truth-value of a statement in NARS is time-dependent in principle, as conceptual relations change over time. However, for efficiency and implementation consideration, it is not always necessary to take the temporal attribution of a statement into account, so, by default, truth-values are not marked with temporal information, and are treated as eternal. Whenever the temporal attribute of a truth-value needs to be specified, the statement is considered an event. Therefore _event_ is not listed in the grammar as a separate category.

**An event** is a statement with a _time-dependent truth value_, that is, the evidential support summarized in its truth-value is valid only in its duration, which is a certain period of time from the moment the event starts to the moment it ends. Thus, an event is a statement whose truth-value may change, and this type of change is different from the changes caused by the accumulation of evidence. During the specified time period of an event, the evidence collected before the period becomes outdated.

## Temporal Relations

In NARS, time can be represented indirectly through events and their temporal relations. The temporal relation between two atomic events E1 and E2 has been designed to fall in one of the following three categories:

1. E1 happens before E2,
2. E1 happens after E2,
3. E1 and E2 happen at the same time.

The first two categories can be expressed using the same temporal relation and therefore, there are _two_ primitive temporal relations: **“before”** and **“when”**. **“before”** relation is irreflexive, antisymmetric, and transitive while **“when”** is reflexive, symmetric, and transitive. 

These two temporal relations are not used alone but are combined with statement-level copulas and connectors by creating their temporal variants. It is natural for second temporal relations "when", to represent Events E1 and E2 that happen in the same moment of time using the conjunction operator ("&&") with an explicit indication of the co-occurrence of the two events, so the connector is the "parallel conjunction" ("&|"). On the contrary, the combination of the "before" relation and conjunction produces "sequential conjunction" ("&/"). Consequently, “(&/, E1, E2)” means “E1 occurs before E2”, while “(&|, E1, E2)” means "E1 and E2 happen at the same time". 

There are also the temporal variants of the copulas _implication_ and _equivalence_ (defined in NAL-5). For an implication statement _<S ==> T>_ where _S_ and _T_ are events, three different temporal relations are established:
* _<S =/> T>_ means _S_ happens before _T_, the statement is called “predictive implication”, where _S_ is called a sufficient precondition of _T_, and _T_ a necessary postcondition of _S_.
* _<S =\> T>_ means _S_ happens after _T_, the statement is called “retrospective implication”, where _S_ is called a sufficient postcondition of _T_, and _T_ a necessary precondition of _S_.
* _<S =|> T>_ means _S_ happens at the same time as _T_, the statement is called “concurrent implication”, where _S_ is called a sufficient co-condition of _T_, and _T_ a necessary co-condition of _S_.

Similarly, there are three types of temporal _equivalence_ statement (predictive, retrospective, and concurrent) that are defined in a similar way: _<S </> T>_, _<T <\> S>_ and _<S <|> T>_. Since _<\>_ is the inverse of _</>_, it is not included in Narsese grammar. 

For more complicated temporal relations, additional terms are used to reduce them into the two basic relations. For example, "E1 proceeds E2 by 5 seconds" can be expressed as _(&/, E1, E3, E2)_, where E3 is the event for "5 seconds". Relational terms can also be used to represent the beginning, ending, and duration of an event.

If an absolute time is used to represent the temporal property of event _E_, then that time itself is to be treated as a special event _T_, and these two events, _E_ and _T_, are described as happening at the same time.

## Time Stamps

Being a real-time system, NARS not only needs to "reason about time", but also "reason in time", which demands a personal time monitoring mechanism. The time is then measured by the system’s internal "clock" defined by its own working cycle. Some temporal properties of an event in NARS are specified with respect to the events defined by this internal clock, with the system’s inference cycle as a unit. It is possible for the inference cycle to take a roughly constant time, though this measurement is obviously "subjective", as it is relevant to the unique system only, and different instances of NARS may have different "time" values associated to the same event. 

Ideally, an event can happen in some arbitrary time interval, during which inference rules can be defined on these time intervals, though, in NAL each event is represented by terms whose corresponding time interval might not be specified. Since NARS always assumes less information, the temporal information about a truth-value can be expressed as a point, and referred to as when the corresponding event "happens", though accurately speaking it is just one point in the unspecified interval where the truth-value is valid.

The real-time experience of a NARS is a sequence of Narsese sentences, separated by non-negative numbers indicating the interval in inference cycles between the arriving time of subsequent sentences. That is, let _Si_ be Narsese sentences and _Ni_ be non-negative integers, a section of real-time experience is expressed as string _S1; N1; S2; N2; S3; N3_
which means that sentence _S1_ is received at a certain moment, then, after _N1_ inference cycles, S2 is received etc. If there is no integers between sentences, like in _S1; S2_ the sentences are taken as arriving at the same moment in time.

Every inference step is required to be among sentences whose truth-values are valid at the same time. When the two premises selected have different time stamps attached, one of them (usually the belief) is "projected" into the time of the other (usually the task), with respect to the current time. The corresponding truth-value calculation is specified in [this paper](https://cis.temple.edu/~pwang/Publication/OpenNARS.pdf).





