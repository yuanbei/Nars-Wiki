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

### Priority
As mentioned above, "Bag" is similar to a priority queue however each element is taken out with probability proportional to a priority of an element. Priority identifies importance of an element, that is importance of a task-link, term-link or a concept, the higher the priority, the longer time it will be processed by the system. In OpenNARS a task can be processed  infinite amount of time and time is measured in terms of inference steps, thus a task can be processed using infinite number of inference steps. For example if a system has only single input sentence, it will be converted to a task which will be processing as long as system is running, however if few sentences are given, all of them will turned into task at some point with assigned priority, and a task with a higher priority will **most likely** will be given more inference steps during process than the task with lower priority.

### Durability
 


