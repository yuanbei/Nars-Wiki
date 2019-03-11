This page describes semantics and implementation of "concept" objects in OpenNARS. Information present here is closely related to ["working cycle of the system"](https://github.com/opennars/opennars/wiki/Working-Cycle), ["task management"](https://github.com/opennars/opennars/wiki/Tasks-Management-in-OpenNARS) and [Types of Links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links). Feel free to read those pages for better understanding. 

## Concept Semantics
OpenNARS is implemented using “term logic”, which is is characterized by the use of categorical sentences and syllogistic
inference rules. A property of term logic is that almost all inference rules use two premises which share a term. Term sharing is convenient since it naturally localizes the choice range of beliefs that is associated with participating terms only. For example, if [task](https://github.com/opennars/opennars/wiki/Type-of-Links:-task-and-term-links) <raven --> bird>. is being processed, [beliefs](https://github.com/opennars/opennars/wiki/Tasks-Management-in-OpenNARS)(processed judgements) that can directly interact with it must have terms “raven” or “bird” in it as subject or predicate.

Such logical approach led to organizing all the term-related information into big buckets or objects called concepts. In OpenNARS, all tasks and beliefs that share a common term are collected into a concept object, which is named by the shared term. As a result, any valid inference step necessarily happens within a single concept. Therefore, a concept becomes a unit for resource allocation, which is larger than a task or a belief. The system distributes its resources firstly among the concepts, and then secondly, within each concept, among the tasks and beliefs. The result is a two-level memory structure where each level, the notion of [“bag”](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)) applies. 


Every term within a Narsese statement including statement itself in internal implementation is represented by a concept. For example, statement **<raven --> black>** is represented using three concepts: "raven", "black" and "<raven --> black>". The concept itself is an object, a big chunk of information, that includes much information beyond name of the concept itself. Concept incorporates numerous data structures including two "BAG" data structures where task-links and term-links are stored referred as "Task Bag" and "Term Bag" respectively.

We can describe the memory of NARS as a bag of concepts, with, within each concept, a bag of tasks and a bag of beliefs. 1
For instance, if the statement of a new task is “raven → bird”, then
the task will be put into the task bag of the concept “Craven” and that of
the concept “Cbird”. If the task is a judgment, it will add a corresponding
belief into the belief bag of the two concepts, too. If there is no such concept
(i.e., the term is novel to the system), it will be created as a result of the
acceptance of the task.