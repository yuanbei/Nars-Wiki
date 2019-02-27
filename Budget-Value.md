While [truth](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) and [desire](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples) values are user accessible metrics, budget value is mostly used in internal implementation and are not important in order to use the system. Information present on this page is highly related to internal data structures used in OpenNARS and its control mechanism. Please feel free to read those pages first in order to better understand budget value. 

In OpenNARS every data item is participating in resource competition and use of **Budget Value** allows to assign reasonable amount of resources for important tasks. Budget value is assigned to three types of data items stored in **Bag** data structure: concept, term-link and task-link. In each working cycle, only the directly related items will have their budget values adjusted, which means the system may need to decide for an item its short and long term importance. The system will not attempt to globally traverse each item to neither update budget value nor implement "forgetting".

## Budget Value Semantics

Budget Value is a composition of three rational numbers in range [0,1]: _priority_, _durability_ and _quality_
Below description will be more centered around tasks however it is transferable to other data items stored in bag structures: task-links, term-links and concepts.

### Priority
As mentioned above, "Bag" is similar to a priority queue however each element is taken out with probability proportional to a **priority** of an element. Priority identifies importance of an element, that is importance of a task-link, term-link or a concept, the higher the priority, the longer time it will be processed by the system. In OpenNARS a task can be processed infinite amount of time and time is measured in terms of inference steps, thus a task can be processed using infinite number of inference steps. For example if a system has only single input sentence, it will be converted to a task which will be processing as long as system is running, however if few sentences are given, all of them will be converted into tasks at some point with assigned priority, and a task with a higher priority will **most likely** be given more inference steps to process than the task with lower priority. **Priority** is a relative measurement that is related to priorities of other elements in the bag. Priority on its own has no absolute indication of how many inference steps should be given for a task to process. 

### Durability
Given non-absolute nature of priority, it is necessary to adjust priority during run-time since tasks can become more, less or not important at all. In addition because of insufficient storage and computing resources, it is beneficial to "forget" a task after it becomes unimportant. **Durability** determines how quickly priority should decrease. It can be viewed as aging factor of a priority, it "decays" the priority of a task. 

Priority is adjusted after a task has finished processing and is being returned to a bag. Updated priority is computed by multiplying priority before processing of a task by durability of a task, that is, ***P1 = P0 * D*** where _P1_ is priority after task is being processed, _P0_ priority before task is processed and _D_ is a durability of a task. Thus updated priority is always less then priority before processing of a task and once bag reaches its full capacity, task with lowest priority is being removed from the bag. 

### Quality
Quality shows a long-term importance of a task such that if priority is being decreased it is not removed from "bag" if quality of a task is high. During run-time at a certain point in time, there are many tasks some of which are important immediately that have high priority, low durability and low quality and some that might be important in the future that have lower priority, higher durability and higher quality. Tasks that have high priority **most likely** will be processed sooner for longer period of time but given low durability, after they are returned to "bag" priority will drop considerably and they will be given a small chance to be processed in the future. However tasks with lower priority but higher durability and higher confidence will stay in bag for much longer time since priority will decrease only marginally.

## Budget Value Some Properties
Adjustment of budget values is not a trivial task. There is no absolute correct solution instead an "update policy" has to developed that needs to prioritize system current's demands. The best policy is still being searched and experimented. Properties and computations of budget values below are relevant to current policy used and might change once a better policy is to be discovered.

- As with truth value, no component of Budget Value can reach its extremes of 0 or 1 

- Repeated use of an item usually increases priority. Repeated item as input indicates that something user demands it to be processed, when it is converted to tasks and represented in memory, all corresponding data items will have increased priority. If item is happen to be repeated during derivation it indicates its importence and high chance that it will be demanded in short future, thus its priority is also increased. 

- [Complexity](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS) of an item usually have negative influence on budget value thus less complex items have higher budget values and thus get more resources. 

- The budget of a goal or a question is reduced when the task is partially satisfied. The better the solution is (evaluated by the choice rule), the lower the budget will become. This process and the relative forgetting process will eventually let a task be removed from the system, though it does not necessarily mean that the task has been processed to a certain level of satisfaction.

- A concept is created when an accepted task contains a term for which there is no existing concept. In this case, the initial priority and durability of the concept is determined by those of the task. After that, the budget of the concept is adjusted independently.

## Budget Value Computation

Every Narsese statement is represented using a task, three or more concepts, task-links and term-links. Budget value of input task is a default value which is a hyper-parameter of the system. Budget Value of a derived task is computed based on budget of its parents, inference rule and type of inference used. Budget values of concepts, task-links and term-links are computed based on budget, complexity and [truth expectation](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) of associated tasks.

### Concept update
**Priority** is being increased when a task (to which task-link is pointing) inside a concept is being processed. It is also is increased then task is It is updated using **OR** function in OpenNARS that is "old priority of a concept" **OR** "priority of a task" 

**Durability** is updated by using average of "durability of a concept" and "durability of a task being processed in Task Bag within a concept"

**Quality** is being updated only if a concept participated during [procedural knowledge](https://github.com/opennars/opennars/wiki/Procedural-Inference) inference.

### Task-link update
**Priority** uses "parent task priority" increased by "priority of a term-link from derived task to a given concept"

**Durability** is computed as following: [("durability of a parent task") / ("complexity of derived task")] * ("term link durability from derived task to a concept of given task-link")

**Quality** is ("truth expectation of parent task") / ("complexity of derived task")

### Term-links update
**Priority** is computed using **OR** function as following: ("old priority of a term link") **OR** ("increase by activation of the target concept priority") **OR** ("truth expectation of derived task"/ "complexity of derived task")

**Durability** is computed using **OR** function as following: ("old durability of the term link") **OR** ("truth expectation of derived task" / "complexity of derived task") 

**Quality** always stays as a default value

