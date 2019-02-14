Desire Value applies to [goal](https://github.com/opennars/opennars/wiki/Sentence:-types,-format) sentences and is key element in [procedural knowledge](https://github.com/opennars/opennars/wiki/Procedural-Inference). Desire value has identical to [truth value format](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples) however it has a different semantics.

During run time of a system there are usually multiple conflicting goals exist. Often achieving one goal makes another one harder to be achieved, therefore system must make decision which goal is better to pursue. Furthermore,  goals may not always be related to each other and thus we cannot expect the system to have explicit knowledge to handle goal conflicts. Desire value is a learned metrics that allows system to compare goals and make a selection during goal conflicts.

As mentioned above, desire value has the same format as truth value, and in fact the two metrics are very related. Desire value has frequency and confidence as its components and range is between 0 and 1, also same [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions), [revision and choice rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) are applied to calculate desire value during inference. 

### Theoretical explanation

Suppose the system is asked to achieve goal _G_, then there should be a hypothetical desired state _D_ of the system after the goal is achieved. Then, given the state D one can form the implication statement S, that is **<G ==> D>**, and the truth value of _S_ can either come from input if goal is supplied by the user or be derived in ordinary way as for any [implication statement](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS). Once D is omitted, the truth value of _S_  becomes desire value of G. 

### Implementation

Important to mention that hypothetical desire state _D_ does not exist in implementation, the desire value of a first goal comes from an input, all subsequently goals are learned using [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) and their desire values are computed similarly as described above: <br/>
Suppose there is a goal G and desired state _D_, then implication is formed **<G ==> D> %f1,c1%**, where desire value is f1, c1. Then the system is asked to come up with an operation _A_ such that goal is achieved with certain truth value, i.e. another implication is created **<A ==> G>** %f2,c2% where truth value is f2,c2. Then using truth function for deduction **<A ==> D>** with some computed truth value, this truth value becomes a desire value for a just derived goal _A_. Again in implementation _D_ is not present and deduction is applied to calculate desire value of _A_ using truth value of **<A ==> G>** and desire value of G


