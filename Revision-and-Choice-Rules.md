## Revision Rule
Revision is an inference step in which evidence from different sources is being combined and its truth value revised. 
Suppose there are two tasks with different truth values, for example: 
<br/><br/>
**1. <snow --> {white}>. %9/10, 10/11%** here _(frequency, confidence)_ mean that snow has been observed white 9 times and 1 time it was not white, thus the total evidence is 10, positive evidence is 9/10 and given that by default _k=1_ confidence is 10/11
<br/><br/>
**2. <snow --> {white}>. %3/4, 4/5%** means snow has been observed white 3 times and there are 4 total observations
<br/><br/>
Now suppose these two tasks have disjoint evidential spaces that is they have no overlapping evidence then they can be summarized into a task with revised truth value. Basically the idea is to sum positive and total evidences and pick a function such that it appropriately maps new evidence to relevant _frequency_ and _confidence_ values. Such function is called **revision function**.
<br/><br/>
**Revision function definition:** Given two tasks sharing same concepts, different truth value and disjoint evidential bases, **new** frequency _f_ and confidence _c_ are being defined as

_f = [f1c1(1 − c2) + f2c2(1 − c1)] = [c1(1 − c2) + c2(1 − c1)]_
_c = [c1(1 − c2) + c2(1 − c1)] = [c1(1 − c2) + c2(1 − c1) + (1 − c1)(1 − c2)]_

Here numbers 1 and 2 correspond to _c_ or _f_ from the first or second task
<br/><br/>
Serial number

Forget