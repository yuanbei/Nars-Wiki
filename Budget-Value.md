While [truth](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) and [desire](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples) values measure evidential support and belong to the logic part of NARS, budget value is about resource allocation and belongs to the control part of NARS. The information present on this page is highly related to the [data structures](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)) used in OpenNARS and its [control mechanism](https://github.com/opennars/opennars/wiki/Inference-Control). It may be better to read those pages first in order to understand the budget value. 

## Budget Value Semantics

In OpenNARS many data items are participating in resource competition, and the **Budget Value** of each item indicates the relative amount of resources assigned to it at the moment, within a container **[bag](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure))**. The type of an item may be a [concept](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes), a [task-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links), a [term-link](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links), or something else.

Budget Value is a composition of three rational numbers in the range [0,1]: _priority_, _durability_ and _quality_.

### Priority

A **[bag](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure))** is a data structure that is similar to a priority queue, except that the **priority** of each item in it does not indicate the _order_ by which it is removed, but the _probability_ for that to happen. Therefore, the priority of an item may correspond to its importance or urgency, depending on the type of the item. Intuitively, it expresses how "active" the item is.

Accurately speaking, the priority of an item is positively correlated with its probability to be selected in the next round of selection within the bag, that is, the higher its priority, the higher its probability to be selected. Moreover, priority is a _relative_ measurement, since the actual probability for an item to be selected not only depends on its own priority value, but also the priority values of the other items in the same bag at the moment. 

### Durability

Given the changing environment, it is necessary to adjust priority values during run-time. One of the principles in resource allocation is to favor the items that are directly related to the current context. It means that the irrelevant items will be gradually ``forgotten.''

Since different items should be forgotten at different rates, the **Durability** of an item determines how quickly its priority should be decreased. It can be viewed as an "aging" or "decaying" factor of the corresponding priority value. That is, after a constant amount of time, the priority value of an item is decreased from _P0_ to _P1 = P0 * D_, where _D_ is the durability value of the item.

Ideally, the priority values of all data items in the system should decay all the time in this manner, the forgetting mechanism cannot be directly implemented in this way, given the insufficient processing time. Therefore, in each [working cycle](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS), only a constant number of data items are "touched" and have their budget values adjusted afterward. One of the aspects of the adjustment is to change the priority value from _P0_ to _P1 = P0 * D^T_, where _T_ is the number of cycles since the previous priority decay, that is, this adjustment achieves the accumulated effects of _T_ adjustments the item should have gone through.

### Quality

Quality shows the long-term significance of a data item to the system, independent to the current context. It is evaluated differently for different types of item and may be adjusted according to the collected feedback on the usage of the item.

In the OpenNARS implementation, the quality value of an item corresponds to a priority value that does not decay anymore, so can be seen as its "baseline activation".

## Budget-Value Properties

Adjustment of budget values is not a trivial task. There is no absolute correct solution, instead, an "update-policy" has to developed that needs to prioritize system current's demands. The best policy is still being searched and experimented. Properties of budget values below are relevant to the current policy used and might change once a better policy is discovered.

- Like truth values, a component of Budget Value rarely reaches its extremes of 0 or 1. 

- Repeated occurrences of an item get merged and lead to an increase in its priority.  

- [Complexity](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS) of an item usually have a negative influence on quality value, thus less complex items get more resources. 

- The budget of a goal or a question is reduced when the task is partially satisfied. The better the solution is (evaluated by the choice rule), the lower the budget will become. This process and the relative forgetting process will eventually let a task be removed from the system, though it does not necessarily mean that the task has been processed to a certain level of satisfaction.

- A concept is created when an accepted task contains a term for which there is no existing concept. In this case, the initial priority and durability of the concept are determined by those of the task. After that, the budget of the concept is adjusted independently.

- Different combinations of the components allow differently budgets. For example, a <high-priority, low-durability, low-quality> budget is for an item that is currently under attention but will be forgotten soon, while a <low-priority, high-durability, high-quality> budget is for an item that is under long-term processing in the background.

In each working cycle budget value is being updated by the related [budget functions](https://github.com/opennars/opennars/wiki/Budget-Update).
