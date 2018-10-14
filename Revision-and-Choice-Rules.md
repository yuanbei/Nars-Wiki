## I. Revision Rule
Revision is an inference process in which evidence from different sources is being combined and its truth value revised. 
Suppose there are two tasks with different truth values, for example: 
<br/><br/>
**1. <snow --> {white}>. %9/10, 10/11%** here _(frequency, confidence)_ mean that snow has been observed white 9 times and 1 time it was not white, thus the total evidence is 10, positive evidence is 9/10 and given that by default _k=1_ confidence is 10/11
<br/><br/>
**2. <snow --> {white}>. %3/4, 4/5%** means snow has been observed white 3 times and there are 4 total observations
<br/><br/>
Now suppose these two tasks have disjoint evidential spaces that is they have no overlapping evidence then they can be summarized into a task with revised truth value. Basically the idea is to sum positive and total evidences and pick a function such that it appropriately maps new evidence to relevant _frequency_ and _confidence_ values. Such function is called **revision function**.
<br/><br/>
**Revision function definition:** Given two tasks sharing same concepts, different truth value and disjoint evidential bases, **new** frequency _f_ and confidence _c_ are being defined as

_f = [ f1c1(1 − c2) + f2c2(1 − c1) ] = [ c1(1 − c2) + c2(1 − c1) ]_ <br/>
_c = [ c1(1 − c2) + c2(1 − c1) ] = [ c1(1 − c2) + c2(1 − c1) + (1 − c1)(1 − c2) ]_

Here numbers 1 and 2 correspond to _c_ or _f_ from the first or second task<br/>
**Properties:** <br/>
* Order of tasks is not important
* Similar to weighted average of _f1_ and _f2_, new _f_ is usually closer to the one that has more evidence that is whose value of _c_ is bigger
* Value of new _c_ is never less than either _c1_ or _c2_
<br/><br/>

### Evidential base
Each task in a system is assigned a _serial number_. During derivation process the derived task stores the serial numbers of the tasks it is derived from in a list which is called **evidential base**. Derivation process is similar to a tree where two parent-tasks create derived child-task after a certain inference step. Evidential base of a child is a union of evidential bases of its parents, and each task has at least one element in its evidential base, its serial number. Obviously, after numerous inference steps it is technically impossible to store all parent' serial numbers in child's evidential base and current implementation limits the length of evidential base to 4 elements. Thus it is possible that after some derivation steps, early task' serial numbers have been lost and it is exactly what system tries to simulate, the concept of biological memory. Human do not remember all the information that leaded to a certain conclusion, this idea is reflected in evidential base, storing serial numbers of tasks that only recently participated in derivation process.

### Overlapping Evidence
For two tasks if they share one or more same elements within their evidential bases, their evidence is **overlapped** i.e. they do not have disjoint evidential base. Ideally when combining evidence, and if some portion of evidence is present more than once, it should be subtracted from final result, however since it is impossible to determine exact amount of some portion of evidence influencing certain task this can't be done. **Therefore revision rule applies only if tasks have disjoint evidential bases that is they do not share common elements.**

## II. Choice Rule
Choice rule is applicable in multiple scenarios.
1. Two tasks are based on overlapping evidence and revision rule can not be applied. For example for an evaluative question both candidate answers may contain same task but different truth value and these two conflicting tasks share at least one element in their evidential bias, the **choice rule** chooses the task with higher _confidence_ value. The intuition is that system makes a choice toward more experience of the task. 

2. 
