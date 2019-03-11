## Introduction

The following page will be related to Budget Value pages, feel free to read [part I](https://github.com/opennars/opennars/wiki/Budget-Value) and [part II](https://github.com/opennars/opennars/wiki/Budget-Update) of Budget value for better understanding of information present here.

Being a real-time dynamic system that always operates under AIKR, OpenNARS always faces an optimization problem: given finite processing time and storage space, find the best allocation strategy to satisfy the demands as much as possible.

There are many formal models for such problems, but none of them can be used in OpenNARS, because their assumptions cannot be satisfied even approximately. For instance, here it cannot be assumed that the problems occur according to a probability distribution (even a unknown one), nor that the problems will appear at specific time. New models need to be developed.

A major job of OpenNARS [control mechanism](https://github.com/opennars/opennars/wiki/Working-Cycle) is to select the most proper task (judgment, goal, or question) to carry out at every moment. Given that system usually does not produce "final solution" to tasks, the more beliefs are used on a task, the better the solution will be. Since new tasks may come to the system at any moment, it is usually impossible to devise an algorithm with a resource budget before the processing starts. 

Thus, the objective of OpenNARS is not to process all of its tasks perfectly, not even to process them to a "satisfying level", but to achieve the highest overall efficiency in resource usage. This is achieved by distributing the resources according to priority values summarizing the various factors involved in resource allocation, and to adjust the priority values at run time to reflect the changes in the environment and within the system.

### Bag Data Structure

To realize dynamic resource allocation OpenNARS self-organizes its memory using **Bag** data structure to give data items prioritized treatment. Bag contains items up to a pre-defined constant capacity where each item has budget value. Bag provides three basic operations found in most data structures: (1) put in, (2) take out, and (3) access by key.

1. **put(_item_)** The given item is put into the bag. If there is already an item with the same key, it is being merged with existent one, if the bag already reaches its maximum capacity, an item with the **lowest** priority is removed to free space for the new item.

2. **take()** Item is taken out of the bag, and the probability for an item to be selected is proportional to its priority value.

3. **get(_key_)** The item with the given key, if it exists, is taken out of the bag

The last operation is common, however the first two are different from the regular "insertion" and "deletion" operations, 
since they are designed with AIKR in mind. Concretely, "insertion" recognizes the limited storage space, while "deletion" recognizes the limited processing time. On abstract level bag can be seen as probabilistic priority-queue. It differs from
the ordinary priority-queues in that the items are not removed exactly according to the order of their priority, but probabilistically, with their priority values used to decide their chances in each removal.

## Implementation
Bag is implemented with underlying hash table and bucket-array called "level" in implementation where each bucket implemented using a set. The "put" operation registers the item in the hash table by its key, and stores it in a bucket by its priority. The "take" operation visits the buckets according to a frequency that is propositional to the ranks of the buckets. Final, "get by key" operation directly gets the item via the hash table. Each operation takes a small constant time to finish.

**Future improvements:** Currently the probability of an item to be taken out is proportional to its priority value. It may be necessary to add a parameter to control the evenness of the probability.

## System Memory
"Bags" are used to store most of the items in OpenNARS including _task-links_, _term-links_ and _concepts_. In general, term system's memory refers to the content of a bag of concepts, and [concept](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) is an object itself that contains multiple elements including bag of [task-links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links), bag of [term-links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links) and other elements.