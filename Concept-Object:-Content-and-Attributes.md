
## The notion of "concept" in NARS

In NARS, a **concept** is a unit of storage and processing and is identified by a [term](https://github.com/opennars/opennars/wiki/Term:-types,-format). The meaning of a concept is defined by its experienced relations with the other concepts, so is subjective and dynamic by nature, and used partially each time the concept is involved in a reasoning process.

[NAL](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-the-logic-behind-OpenNARS) is a _term logic_, which is characterized by the use of categorical sentences and syllogistic inference rules. A property of term logic is that almost all inference rules use two premises which share a term. Term sharing is convenient since it naturally localizes the choice range of beliefs that are associated with participating terms only. For example, if the [task](https://github.com/opennars/opennars/wiki/Type-of-Links:-task-and-term-links) _<raven --> bird>_ is being processed, [beliefs](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS) that can directly interact with it need to have terms _raven_ or _bird_ in it as subject or predicate.

This feature leads NARS to organize all the term-related information into big buckets or objects called **concepts**. In OpenNARS, all tasks and beliefs that share a common term are collected into a concept object, which is named by the shared term. As a result, any valid inference step necessarily happens within a single concept. Therefore, a concept becomes a unit for resource allocation, which is larger than a task or a belief. The system distributes its resources firstly among the concepts, and then secondly, within each concept, among the tasks and beliefs which are also stored using [bags](https://github.com/opennars/opennars/wiki/Memory-Overview), which is a probabilistic priority queue. The result is a [two-level memory structure](https://github.com/opennars/opennars/wiki/Memory-Overview) that acknowledge the insufficiency of time and space resources. Thus we can roughly describe the system's memory as a bag of concepts, with, within each concept, a bag of tasks and a bag of beliefs. 

This concept-centered architecture also supports distributed implementation, as well as the possible special hardware in the future, as the concepts can be handled independently.

## The Concept class

The Java class _Concept_ contains the following content

* The term naming the concept.
* A bag of term links referring to the syntactically related terms. For example, in the concept _[black]_, there are links to _black_ and _<crow --> [black]>_, and those two will link back.
* A bag of task links referring to the syntactically related tasks. For example, the task _<raven --> [black]>._ can be directly accessed from three concepts: _raven_, _[black]_ and _<raven --> [black]>_.
* A belief table, if the concept corresponding to a statement. For example, in concept _<raven --> [black]>_ the truth-values of this statement is stored in such a table, while in concepts _raven_ and _[black]_ there is no such a table.
* A desire table for the goals, similar to the belief table.
* A table of pending questions (queries) on the beliefs (desires).

![concept](https://user-images.githubusercontent.com/24262360/54101472-439e8e80-439a-11e9-9eb1-f4b439703489.png)

As one might observe, we can talk about "the meaning of a concept" in the same way as a "the meaning of a term": just like the meaning of term is determined by its experienced relations with other terms, the meaning of a concept is determined by its experienced relations with other concepts. The difference is just that a term is a symbol, while a concept is a data structure named by a term. We can see that using "concept" approach data items are being localized to items associated to the given concept or term thus addressing insufficient resource issue. With each inference cycle a concept is being selected from the bag with probability propositional to it's budget value and then the system will allocate resources to process items within the concept. For inference cycle of the system please look [here](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)


