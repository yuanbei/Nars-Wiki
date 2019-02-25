While [truth](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) and [desire](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples) values are user accessible metrics, budget value is mostly used in internal implementation and are not important in order to use the system. Information present on this page is highly related to internal data structures used in OpenNARS and its control mechanism. Please feel free to read those pages first in order to better understand budget value. 

## Background

OpenNARS uses "BAG" data structure which on abstract level can be viewed as priority queue with probabilistic behavior of _get()_ operation, that is an item is removed from the queue with some probability. Such  data structure is used to store most of the information present during system's run-time, including _task-links_, _term-links_ and _concepts_.

### Concept
Every term within a Narsese statement including statement itself in internal implementation is represented by a concept. For example, statement **<raven --> black>** is represented using three concepts: "raven", "black" and "<raven --> black>". The concept itself is an object, a big chunk of information, that includes much information beyond name of the concept itself. Concept incorporates numerous data structures including two "BAG" data structures where task-links and term-links are stored referred as "Task Bag" and "Term Bag" respectively.

### Task and Task-Link
As mentioned on previous pages, input and output of OpenNARS are Narsese [sentences](https://github.com/opennars/opennars/wiki/Sentence:-types,-format). Every sentence, either input or derived, becomes a **task** that is being processed and participate in Forward or Backward inference. Task is nothing but a Narsese statement with derived **truth value** (using truth functions, choice or revision rules) **and** assigned **budget value**. Task-link is a link pointing to a task. Task-link is being assigned a **budget value** which is initialized with a budget value of a task it points to and task-link's budget value is being recomputed during inference process. For the above example **<raven --> black>**, concept **raven** has a "Task Bag" where one of elements is a task-link pointing to task **<raven --> black>**.  

### Term-link
Term-link is a link that points to a term from which a statement is composed. For above Narsese statement within concept for "<raven --> black>" there is a "Bag" with two term-links to "raven" and "black". 
 
Thus **Budget Value** is assigned to three types of items stored in **Bags**: concept, term-link and task-link and is re-computed with each inference step for items participating in inference.

## Budget Value Semantics

Budget Value is a composition of three rational numbers in range [0,1]: _priority_, _durability_ and _quality_
Below description will be more centered around tasks however it is transferable to task-links, term-links and concepts.

### Priority
As mentioned above, "Bag" is similar to a priority queue however each element is taken out with probability proportional to a **priority** of an element. Priority identifies importance of an element, that is importance of a task-link, term-link or a concept, the higher the priority, the longer time it will be processed by the system. In OpenNARS a task can be processed infinite amount of time and time is measured in terms of inference steps, thus a task can be processed using infinite number of inference steps. For example if a system has only single input sentence, it will be converted to a task which will be processing as long as system is running, however if few sentences are given, all of them will be converted into tasks at some point with assigned priority, and a task with a higher priority will **most likely** be given more inference steps to process than the task with lower priority. **Priority** is a relative measurement that is related to priorities of other elements in the bag. Priority on its own has no absolute indication of how many inference steps should be given for a task to process. 

### Durability
Given non-absolute nature of priority, it is necessary to adjust priority during run-time since tasks can become more, less or not important at all. In addition because of insufficient storage and computing resources, it is beneficial to "forget" a task after it becomes unimportant. **Durability** determines how quickly priority should decrease. It can be viewed as aging factor of a priority, it "decays" the priority of a task. 

Priority is adjusted after a task has finished processing and is being returned to a bag. Updated priority is computed by multiplying priority before processing of a task by durability of a task, that is, ***P1 = P0 * D*** where _P1_ is priority after task is being processed, _P0_ priority before task is processed and _D_ is a durability of a task. Thus updated priority is always less then priority before processing of a task and once bag reaches its full capacity, task with lowest priority is being removed from the bag. 

### Quality
Quality shows a long-term importance of a task such that if priority is being decreased it is not removed from "bag" if quality of a task is high. During run-time at a certain point in time, there are many tasks some of which are important immediately that have high priority, low durability and low quality and some that might be important in the future that have lower priority, higher durability and higher quality. Tasks that have high priority **most likely** will be processed sooner for longer period of time but given low durability, after they are returned to "bag" priority will drop considerably and they will be given a small chance to be processed in the future. However tasks with lower priority but higher durability and higher confidence will stay in bag for much longer time since priority will decrease only marginally.

## Budget Value Computation

Every Narsese statement is represented using a task, three or more concepts, task-links and term-links. Budget value of input task is a default value which is a hyper-parameter of the system. Budget Value of a derived task is computed based on budget of its parents, inference rule and type of inference used. Budget values of concepts, task-links and term-links are computed based on budget, complexity and [truth expectation](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) of associated tasks.

### Concept update
**Priority** is being increased when a task (to which task-link is pointing) inside a concept is being processed. It is updated using **OR** function in OpenNARS that is "old priority of a concept" **OR** "priority of a task" 

**Durability** is updated by using average of "durability of a concept" and "durability of a task being processed in Task Bag within a concept"

**Quality** is being updated only if a concept participated during [procedural knowledge](https://github.com/opennars/opennars/wiki/Procedural-Inference) inference.

### Task-link update
**Priority** uses "parent task priority" increased by "priority of a term-link from derived task to a given concept"

**Durability** is computed as following: [("durability of a parent task") / ("complexity of derived task")] * ("term link durability from derived task to a concept of given task-link")

**Quality** is ("truth expectation of parent task") / ("complexity of derived task")

### Term-links update
**Priority** is computed using **OR** function as following: ("old priority of a term link") **OR** "increase by activation of the target concept priority") **OR** ("truth expectation of derived task"/ "complexity of derived task")

**Durability** is computed using **OR** function as following: ("old durability of the term link") **OR** ("truth expectation of derived task" / "complexity of derived task") 

**Quality** always stays as a default value

