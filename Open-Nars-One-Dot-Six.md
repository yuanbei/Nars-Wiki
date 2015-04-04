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

