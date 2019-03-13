Information on this page is related to [memory structure](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)) of OpenNARS and [working cycle](https://github.com/opennars/opennars/wiki/Working-Cycle) of the system. Please read those pages for better understanding. 

### Background
Similarly to [concepts](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) Task-link and term-link refer to **data items** in OpenNARS but are unlike concepts term and task links are trivial pointers that are stored in ["bags"](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)) within concept object.

### Task and Task-Link
As mentioned on other pages, input and output of OpenNARS are Narsese [sentences](https://github.com/opennars/opennars/wiki/Sentence:-types,-format). Every sentence, either input or derived, becomes a **task** that is being processed and participate in Forward or Backward inference. Task is nothing but a Narsese statement with input or derived **truth value** (using truth functions, choice or revision rules) **and** associated [concept](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) with assigned [**budget value**](https://github.com/opennars/opennars/wiki/Budget-Value). 

**Task-link** is a link(pointer) pointing from a concept to associated task (for concept for the task it points to itself). Because task-links are stored in "bag" it is being assigned a **budget value** which is initialized with a budget value of a task it points to and task-link's budget value is being recomputed during inference process. 

### Term-link
Term-link is a link that links terms of statement. It is a pointer that points from a statement concept to terms from which this statement is composed and vise versa. Term-links are also stored in "bag" within the concept and thus has budget value assigned. Unlike task-links which are uni-directional, term-links are bi-directional, although in implementation there are actually two term-links one for each direction because each has different budget value assigned.

Now it is clear that a system memory looks like a weighted [graph](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)) with two  types of edges where nodes are concepts, edges are term and task links, and weights are budget values of term and task links. Let's look at the simple example below that will clearly show term and task links. 

### Example
Consider two Narsese input sentences:

**<raven --> bird>. %1.0;0.9%**<br/>
**<bird --> animal>. %1.0;0.9%**<br/>

Then system will create the following concepts with following [belief table](https://github.com/opennars/opennars/wiki/Data-structure-for-evidential-basis,-beliefs-and-goals), term and task links. Please note: the budget value is not present here for simplicity.

Concept **<raven --> bird>** <br/>
Task-links to concepts: <raven --> bird> (task link is a self loop since it is the concept for task itself) <br/>
Belief table: <raven --> bird>.%1.0;0.9% <br/>
Term-links to concepts: raven, bird <br/>

Concept **raven** : <br/>
Task-links to concepts: <raven --> bird> <br/>
Belief table: Empty <br/>
Term-links to concepts: <raven --> bird> <br/>

Concept **bird**: <br/>
Task-links to concepts: <raven --> bird>, <bird --> animal> <br/>
Belief table: Empty <br/>
Term-links to concepts: <raven --> bird>, <bird --> animal> <br/>

Concept **animal**:<br/>
Task-links to concepts: <bird --> animal> <br/>
Belief table: Empty <br/>
Term-links to concepts: <bird --> animal> <br/>

Concept **<bird --> animal>** <br/>
Task-links to concepts: <bird--> animal> <br/> (task link is a self loop since it is the concept for task itself) <br/>
Belief table: <bird--> animal>. %1.0;0.9% <br/>
Term-links to concepts: bird, animal> <br/>

Now consider two concepts **<raven --> bird>** and **raven**. **<raven --> bird>** has term-link to **raven** and **raven** also has a term-link to **<raven --> bird>**. This is **not** bi-directional link but two **different** term-links because they have different budget value. 

Below graph is for above example for clear representation. Concepts are yellow, task-links are red while term-links are blue. _b_ stands for budget value.

![term/task-links](https://user-images.githubusercontent.com/24262360/54265915-ba7b8900-454c-11e9-985a-cedc2d15bba1.png)