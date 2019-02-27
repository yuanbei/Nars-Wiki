## Background

OpenNARS uses "BAG" data structure which on abstract level can be viewed as priority queue with probabilistic behavior of _get()_ operation, that is an item is removed from the queue with some probability. Such  data structure is used to store most of the information present during system's run-time, including _task-links_, _term-links_ and _concepts_.

### Concept
Every term within a Narsese statement including statement itself in internal implementation is represented by a concept. For example, statement **<raven --> black>** is represented using three concepts: "raven", "black" and "<raven --> black>". The concept itself is an object, a big chunk of information, that includes much information beyond name of the concept itself. Concept incorporates numerous data structures including two "BAG" data structures where task-links and term-links are stored referred as "Task Bag" and "Term Bag" respectively.

### Task and Task-Link
As mentioned on previous pages, input and output of OpenNARS are Narsese [sentences](https://github.com/opennars/opennars/wiki/Sentence:-types,-format). Every sentence, either input or derived, becomes a **task** that is being processed and participate in Forward or Backward inference. Task is nothing but a Narsese statement with derived **truth value** (using truth functions, choice or revision rules) **and** assigned **budget value**. Task-link is a link pointing to a task. Task-link is being assigned a **budget value** which is initialized with a budget value of a task it points to and task-link's budget value is being recomputed during inference process. For the above example **<raven --> black>**, concept **raven** has a "Task Bag" where one of elements is a task-link pointing to task **<raven --> black>**.  

### Term-link
Term-link is a link that points to a term from which a statement is composed. For above Narsese statement within concept for "<raven --> black>" there is a "Bag" with two term-links to "raven" and "black". 