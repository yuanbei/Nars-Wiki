These two rules are called "local rules" as they do not generate any new statement, and only work on the existing ones locally. 

## I. Revision Rule
Revision is an inference process in which evidence from different sources is being combined in the conclusion. 
Suppose there are two judgments with the same statement but different truth values, for example: 
<br/><br/>
**1. <snow --> [white]>. %9/10, 10/11%** here _(frequency, confidence)_ means that snow has been observed white 9 times and 1 time it was not white, thus the total evidence is 10, positive evidence is 9/10 and given that by default _k=1_ confidence is 10/11.
<br/><br/>
**2. <snow --> [white]>. %3/4, 4/5%** means snow has been observed white 3 times and there are 4 total observations
<br/><br/>
Now suppose these two judgments have disjoint evidential bases, which means they have no overlapping evidence, then they can be summarized into a conclusion with combined evidence. Basically, the idea is to sum positive and total evidence and pick a function such that it appropriately maps new evidence to relevant _frequency_ and _confidence_ values. Such function is called **revision function**.
<br/><br/>
**Revision function definition:** Given two judgments with the same statement and disjoint evidential bases, **new** frequency _f_ and confidence _c_ are defined as

_f = [ f1c1(1 − c2) + f2c2(1 − c1) ] / [ c1(1 − c2) + c2(1 − c1) ]_ <br/>
_c = [ c1(1 − c2) + c2(1 − c1) ] / [ c1(1 − c2) + c2(1 − c1) + (1 − c1)(1 − c2) ]_

Here numbers 1 and 2 correspond to _c_ or _f_ from the first or second judgment, respectively.<br/>
For the above example, the conclusion is<br/>
**3. <snow --> [white]>. %12/14, 14/15%**

**Properties:** <br/>
* The order of premises does not matter.
* Similar to a weighted average of _f1_ and _f2_, the new _f_ is usually closer to the one that has more evidence, that is, whose value of _c_ is bigger
* The value of the new _c_ is never less than either _c1_ or _c2_
<br/><br/>

### Overlapping Evidence
If the evidential bases of two truth-values have at least one common element, their evidence is **overlapped** and the revision rule cannot be applied.

## II. Choice Rule
The choice rule is applicable in multiple scenarios.
1. Two judgments have the same statement and are based on overlapping evidence, and the revision rule cannot be applied, then a choice must be made if the truth-value is needed. For example, for an _evaluative_ question, both candidate answers may contain the **same** statement but different truth-values and these two conflicting answers share at least one element in their evidential bases, the **choice rule** chooses the task with **higher _confidence_ value**. The justification is that an adaptive system prefers answer based on more evidence.

2. For the selective question of the form <S --> ?x>? (or <?x --> P>?) the system is asked to find a term in the intension of S (or the extension of P) to replace the query valuable _?x_. For the former question, if there are multiple candidate answers, the one with the highest expectation value is chosen by the choice rule, as it is more likely to be confirmed in the future.

**Definition**  Expectation **_e = c * (f − 0.5) + 0.5_**

**Properties:**
* Truth expectation combines _frequency_ with _confidence_ and maps to a single real number in the range [0,1]
* When _confidence_ is close to 1 (full evidence), _truth expectation_ is close to _frequency_
* When _confidence_ is close to 0 (null evidence), _truth expectation_ is close to 0.5 meaning system may equally encounter a piece of positive or negative evidence.
