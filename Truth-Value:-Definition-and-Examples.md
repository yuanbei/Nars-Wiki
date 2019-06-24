### Definition

In NARS the **truth value** of a statement is the system's degree of belief on it, based on the **evidence** collected from the system's experience.  There are three amounts of evidence: 
* the amount of _positive evidence_ is the number of events that support the statement,
* the amount of _negative evidence_ is the number of events that contradict the statement,
* the amount of _total evidence_ is the sum of the above two.

Consider an example: for the statement "Ravens are black" system encounters 9 ravens that are actually black and 1 that is white. Then the amount of positive evidence will be 9, that of negative evidence will be 1, and that of total evidence will be 10. 

To measure evidential support using relative measurements, a **truth value** is a pair of rational numbers in the range from 0 to 1. The first element of the truth value is **frequency** and the second is **confidence**.

**Frequency** is defined as the proportion of positive evidence among total evidence, that is, _(positive evidence)/(total evidence)_. For the example above, frequency will be 9 / 10 = 0.9. As a special case, when the amount of total evidence is 0, _frequency_ is defined to be 0.5.

Now consider another example: for the same statement "Ravens are black", the system encounters 9000 black ravens and 1000 white ravens, then the _frequency_ of the statement, in this case, will be as before: 9000/10000 = 0.9. However, it is clear that the statement "Ravens are black" is more "certain" in this case than in the previous one. This is why a second measurement, confidence, is used to represent.

**Confidence** indicates how sensitive the corresponding _frequency_ is with respect to new evidence, as it is defined as the proportion of total evidence among total evidence plus a constant amount of new evidence, that is, _(total evidence) / (total evidence + k)_ where _k_ is a system parameter and in most discussions takes the default value of 1. In the first example, confidence = 10 / (10 + 1), around 0.9, while in the second it is 10000/(10000 + 1), around 0.99.

Thus _frequency_ can be seen as the degree of belief system has for the statement and _confidence_ as the degree of belief for that estimation of frequency.

### Examples

In Narsese statements truth value is attached at the end of the statement between percentage (%) symbol. 

For the examples above the valid Narsese statements will be: 
```
<raven --> [black]>. %0.9; 0.9% 
```
Here frequency = 0.9 and confidence = 0.9
```
<raven --> [black]>. %0.9; 0.99% 
```
Here frequency = 0.9 and confidence = 0.99

