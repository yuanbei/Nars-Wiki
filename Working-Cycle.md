# Introduction

Every reasoning system has a "logic" part and a "control" part. The former specifies what can be expressed (the grammar and semantics) and what can be derived in each step (the inference rules), while the latter specifies what tasks can be carried out by linking the inference steps into inference processes. This relation is put into an intuitive formula by Robert Kowalski as "Algorithm = Logic + Control", though it can be extended beyond algorithmic processes.

The logic part of NARS consists of the formal language [Narsese](https://github.com/opennars/opennars/wiki/Input-Output-Format), [Experience-Grounded Semantics (EGS)](http://www.cis.temple.edu/~pwang/Publication/semantics.pdf), and [Non-Axiomatic Logic (NAL)](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) described in "Logic" part on home wiki page. Control Mechanism is physical implementation of the logic part that allows OpenNARS to function and be applied for various purposes.

# Design principle

Traditionally, the control mechanism in a reasoning system depends on either a domain-specific "strong method" or a domain-independent "weak method". In the former case, the inference steps are organized into inference algorithms specially designed for the problem to be solved; in the latter case, some universal algorithm, such as exhaustive research, is applied that does not need domain-specific knowledge. In both cases, the inference process follows an algorithm that is repeatable, either deterministically or probabilistically.

NARS is based on the theory that intelligence is a relative rationality, and an intelligent system should be adaptive and work with insufficient knowledge and resources. Consequently, NARS uses neither the "strong method" nor the "weak method", but works in a "non-algorithmic" manner, by selecting its inference steps at run time, depending on many ever-changing factors. Consequently, an individual inference process, as part of the system's lifelong experience, is not repeatable, even in the probabilistic sense. It is not a "strong method" because NARS is designed to be general-purpose, without assuming any domain knowledge. On the other hand, it is not "weak method", neither, because the system learns domain knowledge gradually, so its selection of steps will become more and more based on its past experience.

Roughly speaking, the function of control mechanism in NARS is to dynamically allocate the system's limited resources to the activities demanding them. The objective is to optimize the expected overall efficiency, estimated according to the system's beliefs summarizing the past experience. Under the assumption of insufficient resources, the system will not be able to satisfy all the resource demands, and under the assumption of insufficient knowledge, there is no guarantee that the selections the system makes are really optimal when judged according to the system's future experience.

# Working Cycle

OpenNars runs by repeating the following working cycle:
1. Probabilistically select a concept C from the memory

2. Probabilistically select a tasklink from C, which specifies the task T to be used

3. Probabilistically select a termlink from C, which specifies the belief B to be used

4. With T and B as premises, trigger the applicable inference rules to derive new tasks and add them into the task buffer

5. Probabilistically select some tasks from the task buffer for pre-processing

Pre-processing of a task means to puts it into the corresponding concepts (and create them if they do not exist). Within a concept, the new task may create new belief, revise existing beliefs, satisfy a goal, or answer a question. If an input question obtains a best-so-far answer, it will be reported.
