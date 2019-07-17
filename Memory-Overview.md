## Introduction

Being a real-time dynamic system that always operates under AIKR, NARS always faces an optimization problem: given finite processing time and storage space, find the best allocation strategy to satisfy the demands as much as possible.

There are many formal models for such problems, but none of them can be used in OpenNARS, because their assumptions cannot be satisfied even approximately. For instance, here it cannot be assumed that the problems occur according to a probability distribution (even an unknown one), nor that the problems will appear at specific moments. Therefore the approach used in NARS is very different from the traditional ones.

A major job of OpenNARS [control mechanism](https://github.com/opennars/opennars/wiki/Inference-Control) is to select the most proper task (judgment, goal, or question) to be processed at every moment, as well as the most suitable beliefs to process it. Given that the system usually does not produce "final solution" to tasks, the more beliefs are used on a task, the better the solution will be. Since new tasks may come to the system at any moment, it is usually impossible to devise an algorithm with a resource budget before the processing starts. 

Thus, the objective of OpenNARS is not to process all of its tasks perfectly, not even to process them to a "satisfying level", but to achieve the highest overall efficiency in resource usage. This is achieved by distributing the resources among data items according to their priority values summarizing the various factors involved in resource allocation, and to adjust the priority values at run time to reflect the changes in the environment and within the system.

## Bag Data Structure

To realize dynamic resource allocation OpenNARS self-organizes its memory using a "bag" data structure to give data items prioritized treatment. Bag contains items up to a pre-defined constant capacity where each item has a [budget value](https://github.com/opennars/opennars/wiki/Budget-Value). Bag provides three basic operations found in most data structures: (1) put in, (2) take out, and (3) access by key.

1. **put(_item_)** The given item is put into the bag. If there is already an item with the same key, it is being merged with existent one; if the bag already reaches its maximum capacity, an item with the **lowest** priority is removed to free space for the new item.

2. **take()** An item is selected probabilistically and taken out of the bag, and the probability for an item to be selected is positively correlated with its priority value.

3. **get(_key_)** The item with the given key, if it exists, is taken out of the bag.

The last operation is common, however, the first two are different from the regular "insertion" and "deletion" operations, since they are designed with AIKR in mind. Concretely, "insertion" recognizes the limited storage space, while "deletion" recognizes the limited processing time. On abstract level bag can be seen as probabilistic priority-queue. It differs from the ordinary priority-queues in that the items are not removed exactly according to the order of their priority, but probabilistically, with their priority values used to decide their chances in each removal.

## Implementation

In OpenNARS, bag is implemented with an underlying hash table and bucket-array called "level" where each bucket is implemented using a list. The "put" operation registers the item in the hash table by its key, and stores it in a bucket by its priority. The "take" operation visits the buckets according to a frequency that is correlated with the ranks of the buckets. Final, "get by key" operation directly gets the item via the hash table. Each operation takes a small constant time to finish.

Since AIKR must be respected everywhere in OpenNARS, bags are used to store several types of data items, so the class is specified as generic, with a parameter for the type of data item in it, such as _concept_, _task_, etc. Every data type to be maintained in a bag must implement the abstract class _Item_, which will require a [budget value](https://github.com/opennars/opennars/wiki/Budget-Value) for each item.

**Future improvements:** Currently the probability of an item to be taken out is proportional to its priority value. It may be necessary to add a parameter to control the evenness of the probability.

## System Memory

The system's memory contains a bag of [concept](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes), plus several buffers and tables, such as a bag of new tasks to be processed, a table of registered operators, etc. 

The memory can be roughly visualized as a concept network where each concept is named by a term. When the system runs, the network's topological structure changes, with new nodes and links added and removed, and the contents of the nodes and links are modified, too, both because of the coming of new experience (input stream) and the reasoning activities of the system itself.
