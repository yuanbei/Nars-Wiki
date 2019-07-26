
### Task-link

Each input and output of OpenNARS is a Narsese [task](https://github.com/opennars/opennars/wiki/Task-and-Belief). 

A **Task-link** (instance of the TaskLink class) is a link pointing from a concept to a task that can be processed in the concept.

Because task-links are stored in [bag](https://github.com/opennars/opennars/wiki/Memory-Overview#bag-data-structure), it is assigned a [budget value](https://github.com/opennars/opennars/wiki/Budget-Value) which is initialized with a budget value of a task it points to and task-link's budget value is being recomputed during the inference process. 

### Term-link

A term-link links a concept to another concept that is related to it syntactically, i.e., as its component or compound. Term-links are also stored in "bag" within the concept and thus has budget value assigned. Unlike task-links which are uni-directional, term-links are bi-directional, although in implementation there are actually two term-links one for each direction because each has different budget values assigned.

Now it is clear that a system memory looks like a weighted [graph](https://en.wikipedia.org/wiki/Graph_(discrete_mathematics)) with two types of edges where nodes are concepts and tasks, edges are term and task links, and weights are budget values of term and task links. Let's look at the simple example below that will clearly show term and task links. 

### Example

Consider two Narsese input tasks:

**<raven --> bird>. %1.0;0.9%**<br/>
**<bird --> animal>. %1.0;0.9%**<br/>

Then system will create the following [concepts]() with following [belief table](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes), term and task links. Please note: the budget value is not present here for simplicity.

Concept **<raven --> bird>** <br/>
Task-links to task object: _<raven --> bird>. %1.0;0.9%_<br/>
Belief table: <raven --> bird>.%1.0;0.9% <br/>
Term-links to concepts: raven, bird <br/>

Concept **raven** : <br/>
Task-links to task object: _<raven --> bird>. %1.0;0.9%_<br/>
Belief table: Empty <br/>
Term-links to concepts: <raven --> bird> <br/>

Concept **bird**: <br/>
Task-links to task object: _<raven --> bird>. %1.0;0.9%_<br/>
Belief table: Empty <br/>
Term-links to concepts: <raven --> bird>, <bird --> animal> <br/>

Concept **animal**:<br/>
Task-links to task object: _<raven --> bird>. %1.0;0.9%_<br/>
Belief table: Empty <br/>
Term-links to concepts: <bird --> animal> <br/>

Concept **<bird --> animal>** <br/>
Task-links to task object: _<bird --> animal>. %1.0;0.9%_<br/>
Belief table: <bird --> animal>. %1.0;0.9% <br/>
Term-links to concepts: bird, animal <br/>

Now consider two concepts **<raven --> bird>** and **raven**. **<raven --> bird>** has term-link to **raven** and **raven** also has a term-link to **<raven --> bird>**. This is **not** bi-directional link but two **different** term-links because they have different budget value. 

The following graph is for the above example for clear representation. Concepts are yellow, task objects are orange, task-links are red while term-links are blue. _b_ stands for budget value.

![term/task-links](https://user-images.githubusercontent.com/24262360/61977023-44d3ff00-afbb-11e9-8263-17551cab7adb.png)