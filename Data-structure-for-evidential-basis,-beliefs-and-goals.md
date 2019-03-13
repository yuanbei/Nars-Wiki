For evidential basis, beliefs and goals OpenNars uses simple array and list data structures 

## Evidential Basis
To read about Evidential basis please go [here](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules). To represent Evidential basis system uses simple list to store elements. When inference rules are applied to premises the list is being traversed to see the derivation history of a task.

## Belief and Goal tables
Belief and Goal tables are part of the [concept](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) object. Belief is a processed judgment, in other words knowledge base or system's experience, while Goals are tasks that system needs to achieve. Since both, beliefs and goals are sentences they have [truth](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) or [desire](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples) values attached. In OpenNars belief and goal tables are implemented using arrays which are sorted by highest confidence value.

**Future Improvements** for faster sorting and retrieval, belief and goal tables are better implemented using max heaps using max confidence of a sentence.