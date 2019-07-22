## Budget Value Computation

A [budget value](https://github.com/opennars/opennars/wiki/Budget-Value) consists of three factors, <priority, durability, quality>, and is associated with a data item that participates in time-space resource competition in NARS.

Because of the real-time and dynamic nature of NARS, most of the factors are being learned and re-evaluated from time to time, according to context and history. In each working cycle, only the directly related items will have their budget values adjusted (so it can be done in constant time, independent of the size of the memory), which means the system may need to decide for an item its short and long term importance and urgency. The calculations mostly use extended Boolean functions](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS).

Every Narsese statement is represented using a task, three or more concepts, task-links and term-links. Budget value of input task is a default value which is a hyper-parameter of the system. Budget Value of a derived task is computed based on budget of its parents, inference rule and type of inference used. Budget values of concepts, task-links and term-links are computed based on budget, complexity and [truth expectation](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) of associated tasks.

### Concept update
**Priority** is being increased when a task (to which task-link is pointing) inside a concept is being processed. It is also increased concept is being repeatedly used in derivation or input. It is updated using **OR** function in OpenNARS that is "old priority of a concept" **OR** "priority of a task" 

**Durability** highly is dependent on the task currently being processed. It updated by using average of "durability of a concept" and "durability of a task being processed in Task Bag within a concept"

**Quality** for a concept is mostly stays the same. It is updated only if a concept participates during [procedural knowledge](https://github.com/opennars/opennars/wiki/Procedural-Inference) inference.

### Task-link update
**Priority** of task-link depend on parent's priority the task is derived from. It uses "parent task priority" increased by "priority of a term-link from derived task to a given concept"

**Durability** is computed as following: [("durability of a parent task") / ("complexity of derived task")] * ("term link durability from derived task to a concept of given task-link"). Thus complexity negatively influence durability of a task-link which then affects durability of a concept since durability of a concept is an average of concept's and task-link's durability.

**Quality** is affected by a complexity and truth expectation of parent's task. It is updated as following: ("truth expectation of parent task") / ("complexity of derived task")

### Term-links update
**Priority** is computed using **OR** function as following: ("old priority of a term link") **OR** ("increase by activation of the target concept priority") **OR** ("truth expectation of derived task"/ "complexity of derived task")

**Durability** is computed using **OR** function as following: ("old durability of the term link") **OR** ("truth expectation of derived task" / "complexity of derived task") 

**Quality** always stays as a default value