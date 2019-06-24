During the run time of NARS there are usually multiple conflicting [goals](https://github.com/opennars/opennars/wiki/Sentence:-types,-format) exist. Sometimes achieving one goal makes another one harder to be achieved, therefore the system must make a decision on which goal to pursue from moment to moment. As goals may not be directly related to each other in content and thus the system cannot be expected to have explicit knowledge on how to handle goal conflicts and competitions. To solve this problem, each goal is assigned a _desire value_ to indicate its relative significance to the system. It allows the system to compare goals and make a selection during goal conflicts.

Conceptually, the desire value of a goal _G_ is defined to be the truth value of the implication statement _G ==> D_ where _D_ is a virtual statement representing the desired state of the system. That is, "G is desired " is interpreted as "G implies the desired state". Consequently, desire values have the same format as truth values, and are also grounded in the system's experience. The desire values of input goals can be assigned by the user to reflect their relative importance or take default values. Derived goals get their desire values from desire-value functions that are part of the goal-derivation rules.

### Example

Important to mention that hypothetical desire state _D_ does not exist in implementation, the desire value of a first goal comes from an input, all subsequently goals are learned using [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) and their desire values are computed similarly as described above: <br/>
Suppose there is a goal _G_ with desire value %f1;c1%, that is, 
```
    G! %f1;c1%
```
The goal is conceptually interpreted as implication judgment _<G ==> D>. %f1;c1%_ with the desired state _D_. If the system has a belief
```
    <A ==> G>. %f2;c2%_
```
then using the deduction rule the system derives _<A ==> D>. %f3;c3%_, which is interpreted as a goal
```
    A! %f3;c3%
```
In this way, inference rules (not limited to deduction) not only can derive new beliefs but also new goals, with the above interpretation. 



