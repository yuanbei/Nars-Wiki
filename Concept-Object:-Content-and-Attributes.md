This page describes semantics and implementation of "concept" objects in OpenNARS. **Concept** is a major data item in OpenNARS system that is stored in "Bag" data structure and assigned budget value. Information present here is closely related to ["budget value"](https://github.com/opennars/opennars/wiki/Budget-Value), ["working cycle of the system"](https://github.com/opennars/opennars/wiki/Working-Cycle), ["task management"](https://github.com/opennars/opennars/wiki/Tasks-Management-in-OpenNARS) and ["Types of Links"](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links). Feel free to read those pages for better understanding. 

## Concept Semantics
OpenNARS is implemented using “term logic”, which is is characterized by the use of categorical sentences and syllogistic
inference rules. A property of term logic is that almost all inference rules use two premises which share a term. Term sharing is convenient since it naturally localizes the choice range of beliefs that is associated with participating terms only. For example, if [task](https://github.com/opennars/opennars/wiki/Type-of-Links:-task-and-term-links) <raven --> bird>. is being processed, [beliefs](https://github.com/opennars/opennars/wiki/Tasks-Management-in-OpenNARS) (processed judgements) that can directly interact with it must have terms “raven” or “bird” in it as subject or predicate.

Such logical approach led to organizing all the term-related information into big buckets or objects called **concepts**. In OpenNARS, all tasks and beliefs that share a common term are collected into a concept object, which is named by the shared term. As a result, any valid inference step necessarily happens within a single concept. Therefore, a concept becomes a unit for resource allocation, which is larger than a task or a belief. The system distributes its resources firstly among the concepts, and then secondly, within each concept, among the tasks and beliefs which are also stored using "bags". The result is a two-level memory structure where on each level, the notion of [“bag”](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)) is applied. Thus we can describe system memory as a bag of concepts, with, within each concept, a bag of tasks and a bag of beliefs. 

## Implementation
Every [term](https://github.com/opennars/opennars/wiki/Term:-types,-format) within a Narsese statement including statement itself in internal implementation is represented by a **concept**. For example, statement **<raven --> black>** is represented using three concepts: "raven", "black" and "<raven --> black>". The concept itself is an object, a big chunk of information, that includes much information beyond name of the concept itself. Concept incorporates numerous data structures including two "BAGs" data structures where task-links and term-links are stored referred as "Task Bag" and "Term Bag" respectively.

### Concept components:

1. Concept Name which is the same as term name

2. Bag of term links, term-link bag, that is the bag of links (pointers) which point to **terms** this concept is associated with

3. Bag of task links, task-link bag, that is the bag of links (pointers) which point to tasks this concept(term) is part of. If concept is a task itself then task-link is a self-loop 

4. Believe Table: Array sorted by highest confidence. Beliefs (processed judgements) that this concept is associated with 

5. Goal Table: Array sorted by highest confidence. Goals to be achieved associated with this concept

6. Supplementary technical data for implementation

A concept is visualized below for better understanding. Links pointing example is found [here](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links)

![concept](https://user-images.githubusercontent.com/24262360/54101472-439e8e80-439a-11e9-9eb1-f4b439703489.png)

With each inference cycle a concept is being selected from the bag with probability propositional to it's budget value and then the system will allocate resources to process items within the concept. For inference cycle of the system please look [here](https://github.com/opennars/opennars/wiki/Working-Cycle)

 
