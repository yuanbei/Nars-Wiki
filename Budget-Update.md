### Budget Value Computation

A [budget value](https://github.com/opennars/opennars/wiki/Budget-Value) consists of three factors, <priority, durability, quality>, and is associated with a data item that participates in time-space resource competition in NARS.

An input task can be given a budget by the user of the system that assigns this task to NARS, according to the definition of a budget value. The system can also provide default values for the factors, according to the type and other attributes of the task. The budget value of derived tasks, as well as other types of items (beliefs, concepts, links, etc.) are calculated from the budget of the task that creates then, as well as other relevant information that is available at the moment. 

Because of the real-time and dynamic nature of NARS, most of the factors are being learned and re-evaluated from time to time, according to context and history. In each working cycle, only the directly related items will have their budget values adjusted, which means the system may need to decide for an item its short and long term importance and urgency. 

The budget functions mostly consist of [extended Boolean functions](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS), and the budget-related calculation takes roughly constant time in each working cycle, independent of the size of the memory.

There are some general budget adjustment mechanisms that have been mentioned in other pages:
* There is a general [forgetting process](https://github.com/opennars/opennars/wiki/Budget-Value#durability), by which every priority value is decreased according to the durability value until it reaches the quality value.
* Repeated items in the same bag [are merged](https://github.com/opennars/opennars/wiki/Memory-Overview#bag-data-structure), with the new priority being the **OR** of those being merged.

In the following, only the type-specific budget calculations are described.

### Concept budget

The **priority** of a concept is being increased when a task is added into the concept (i.e., a task-link is put into the task bag). The updating uses the **OR** function with the "old priority value of the concept" and the "priority of the task" as arguments.

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