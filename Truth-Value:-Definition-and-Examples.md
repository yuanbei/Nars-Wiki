### Definition

One of most crucial metrics in OpenNARS is **truth value** that shows the degree of believe of given statement and is based on **evidence** collected from prior inferences or input.  There are three types of evidence: positive, negative and total evidence: 

_Positive evidence_ is the number that shows number of events that supports given statement. 

_Negative evidence_ is the number that shows number of events that contradicts given statement.

_Total evidence_ is sum of positive and negative evidence.

Consider an example: for the statement "raven is black" system encounters 9 ravens that are actually black and 1 that is white. Then positive evidence will be 9, negative evidence will be 1 and total evidence will be 10. 

**Truth value** is a tuple of rational numbers in range from 0 to 1 that is nothing but proportion of different types of evidences.

The first element of the truth value is **frequency** and the second is **confidence**

**Frequency** is a measurement of uncertainty it is defined as proportion of positive evidence among total evidence that is _(positive evidence)/(total evidence)_, for the example above frequency will be 9 / 10 = 0.9. As a special case when total evidence is 0 and therefore positive evidence is also 0 _frequency_ is defined to be 0.5

Now consider another example: for the same statement "raven is black" system encounters 9000 ravens that are black and 1000 white ravens then positive evidence will be 9000, negative evidence will be 1000 and total evidence will be 10000. 
_Frequency_ in this case will be as before 9000/10000 = 0.9 however it is clear that statement "raven is black" is more "certain" than before, in other words we convinced more that the ravens are black from the second example more than from the first.

**Confidence** is a degree of believe for the statement with given _frequency_ and shows how much evidence does system has for derived _frequency_. _Confidence_ also shows how long the frequency of the statement will be sustained in the future while system makes inferences. _Confidence_ is defined as _(total evidences) / (total evidence + k)_ where _k_ is constant and system hyper parameter and usually _k = 1_. In the first example, confidence = 10 / (10 + 1) = 0.9 while for the second it is 10000/(10000 + 1) = 0.99

Thus _frequency_ can be seen as degree of certainty system has for the statement and _confidence_ degree of believe in that certainty.

### Examples

In Narsese statements truth value is attached at the end of the statement between percentage (%) symbol. 

For the examples above the valid Narsese statements will be: 

<raven --> [black]>. %0.9, 0.9% Here frequency = 0.9 and confidence = 0.9
<raven --> [black]>. %0.9, 0.99% Here frequency = 0.9 and confidence = 0.99

