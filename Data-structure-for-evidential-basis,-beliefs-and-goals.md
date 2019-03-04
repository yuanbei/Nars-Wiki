For evidential basis, beliefs and goals OpenNars uses simple array and list data structures 

## Evidential Basis
To read about Evidential basis please go [here](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules). To represent Evidential basis system uses simple list to store elements. When inference rules are applied to premises the list is being traversed to see the derivation history of a task.

## Belief and Goal tables
Belief is a processed judgment, in other words knowledge base or systems experience, while Goals are tasks that system needs to achieved. Since both, beliefs and goals are sentences they have truth or desire values attached. In OpenNars belief and goal tables are implemented using arrays which are sorted by highest confidence value.

**Future Improvements** for faster sorting and retrieval, belief and goal tables are better implemented using max heaps using max confidence of a sentence.