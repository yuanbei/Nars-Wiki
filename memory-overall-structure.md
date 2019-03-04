## Introduction

The following page will be related to Budget Value pages, feel free to read [part I](https://github.com/opennars/opennars/wiki/Budget-Value) and [part II](https://github.com/opennars/opennars/wiki/Budget-Update) of Budget value for better understanding of information present here.

Being a real-time dynamic system that always operates under AIKR, OpenNARS always faces an optimization problem: given finite processing time and storage space, find the best allocation strategy to satisfy the demands as much as possible.

There are many formal models for such problems, but none of them can be used in OpenNARS, because their assumptions cannot be satisfied even approximately. For instance, here it cannot be assumed that the problems occur according to a probability distribution (even a unknown one), nor that the problems will appear at specific time. New models need to be developed.

A major job of OpenNARS [control mechanism](https://github.com/opennars/opennars/wiki/Working-Cycle) is to select the most proper task (judgment, goal, or question) to carry out at every moment. Given that system usually does not produce "final solution" to tasks, the more beliefs are used on a task, the better the solution will be. Since new tasks may come to the system at any moment, it is usually impossible to devise an algorithm with a resource budget before the processing starts. 

Thus, the objective of OpenNARS is not to process all of its tasks perfectly, not even to process them to a "satisfying level", but to achieve the highest overall efficiency in resource usage. This is achieved by distributing the resources according to priority values summarizing the various factors involved in resource allocation, and to adjust the priority values at run time to reflect the changes in the environment and within the system.

### Bag Data Structure

To realize dynamic resource allocation, NARS self-organizes its memory using probabilistic priority-queue to give data items prioritized treatment. A bag is a data structure with the basic operations (1) put in, (2) take out, and (3) access by key. The take-out operation is probabilistic, according to the priority distribution of the items in the bag. Each operation takes a small constant time to finish.

**Issue:** Currently the probability of an item to be taken out is proportional to its priority value. It may be necessary to add a parameter to control the evenness of the probability.

Since NAL is a term logic, its inference rules typically require shared term in premises, so tasks and beliefs can be indexed and clustered by their component terms. In NARS, each concept is a data structure named by a term, and it links to the tasks and beliefs with the term in it. Consequently, a concept is an independent unit of storage and processing.

Roughly speaking, the system's memory contains a bag of concepts; a concept contains a bag of task-links referring to the relevant tasks (justment, goal, or question) and a bag of term-links referring to the relevant beliefs (judgments only).

The following figure summarizes the overall architecture and procedure of NARS:

More accurately, the system runs by repeating the following working cycle:

1. Probabilistically select a concept C from the memory

2. Probabilistically select a tasklink from C, which specifies the task T to be used

3. Probabilistically select a termlink from C, which specifies the belief B to be used

4. With T and B as premises, trigger the applicable inference rules to derive new tasks and add them into the task buffer

5. Probabilistically select some tasks from the task buffer for pre-processing

Pre-processing of a task means to puts it into the corresponding concepts (and create them if they do not exist). Within a concept, the new task may create new belief, revise existing beliefs, satisfy a goal, or answer a question. If an input question obtains a best-so-far answer, it will be reported.

A graphical description of how questions are answered by the system by this process:

**Issue:** It may be necessary to add task buffers to each concept to hold the tasks added, so as to postpone their preprocessing until the concept is selected. Competition can be added into the buffer, so only selected tasks are processed.





OpenNARS uses "BAG" data structure which on abstract level can be viewed as priority queue with probabilistic behavior of _get()_ operation, that is an item is removed from the queue with some probability. Such  data structure is used to store most of the information present during system's run-time, including _task-links_, _term-links_ and _concepts_.



