### Budget Value Computation

A [budget value](https://github.com/opennars/opennars/wiki/Budget-Value) consists of three factors, <priority, durability, quality>, and is associated with a data item that participates in time-space resource competition in NARS.

An input task can be given a budget by the user of the system that assigns this task to NARS, according to the definition of a budget value. The system can also provide default values for the factors, according to the type and other attributes of the task. The budget value of derived tasks, as well as other types of items (beliefs, concepts, links, etc.) are calculated from the budget of the task that creates it, as well as other relevant information that is available at the moment. 

Because of the real-time and dynamic nature of OpenNARS, most of the factors are being learned and re-evaluated from time to time, according to context and history. In each working cycle, only the directly related items will have their budget values updated, which means the system may need to decide for an item its short and long term importance and urgency. 

The budget functions mostly consist of [extended Boolean functions](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS), and the budget-related calculation takes roughly constant time in each working cycle, independent of the size of the memory.

There are some general budget adjustment mechanisms that have been mentioned in other pages:
* There is a general [forgetting process](https://github.com/opennars/opennars/wiki/Budget-Value#durability), by which every priority value is decreased according to the durability value until it reaches the quality value.
* Repeated items in the same [bag](https://github.com/opennars/opennars/wiki/Memory-Overview#bag-data-structure) are merged, with the new priority being as **OR** of those being merged.

Below, only the type-specific budget calculations are described. They are mostly heuristics selected according to the developing and testing results of OpenNARS and need to be refined and put on a more coherent foundation in the future.

### Concept budget

The **priority** of a concept is being increased when a task is added into the concept (i.e., a task-link is put into the task bag). The updating uses the **OR** function with the "old priority value of the concept" and the "priority of the task" as arguments. This is similar to the priming effect in psychology.

The **durability** is updated to the average of the "durability of the concept" and the "durability of the task under processing", so it will be adjusted by taking the task into account.

**Quality** for a concept is mostly stays the same. It is updated only when a concept participates [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference).

### Task-link budget

The initial **priority** of task-link is positively correlated to the priority values of its "parents" (a task and a belief) from which the task is derived. 

The initial **durability** is computed similarly from those of the parents, plus that the complexity of the derived task will have a negative impact, so complicated tasks will be forgotten factor when the other factors are the same.

The initial **quality** is affected by the expectation of the task positively (favoring affirmative tasks) and the complexity of the task negatively (favoring simpler tasks).

### Term-links budget

After each inference step, the **priority** value is updated as the following: ("old priority of the term link") **OR** ("priority of the target concept") **OR** ("expectation of the derived task"/ "complexity of the derived task")

The **durability** is updated as the following: ("old durability of the term link") **OR** ("expectation of the derived task" / "complexity of the derived task") 

**Quality** always stays at a default value.