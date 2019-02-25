While [truth](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) and [desire](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples) values are user accessible metrics, budget value is mostly used in internal implementation and are not important in order to use the system. Information present on this page is highly related to internal data structures used in OpenNARS and its control mechanism. Please feel free to read those pages first in order to better understand budget value. 

### Background

OpenNARS uses "BAG" data structure that on abstract level can be viewed as priority queue with probabilistic behavior of _get()_ operation.  Such  data structureis used to store most of the information present during system runtime. 


### Description of Budget Value

