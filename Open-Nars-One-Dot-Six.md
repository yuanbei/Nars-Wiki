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