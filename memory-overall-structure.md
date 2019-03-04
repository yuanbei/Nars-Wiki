## Background

OpenNARS uses "BAG" data structure which on abstract level can be viewed as priority queue with probabilistic behavior of _get()_ operation, that is an item is removed from the queue with some probability. Such  data structure is used to store most of the information present during system's run-time, including _task-links_, _term-links_ and _concepts_.



