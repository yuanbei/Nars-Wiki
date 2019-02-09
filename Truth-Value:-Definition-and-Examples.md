### Definition

One of most crucial metrics in OpenNARS is **truth value** that shows the degree of believe of given statement and is based on **evidence** collected from prior inferences or input. 

There are three types of evidence: positive, negative and total evidence: 
_Positive evidence_ is the number that shows number of events that supports given statement.
_Negative evidence_ is the number that shows number of events that contradicts given statement.
_Total evidence_ is sum of positive and negative evidence.

For example for the statement "raven is black" system encounters 9 ravens that are actually black and 1 that is white. Then positive evidence will be 9, negative evidence will be 1 and total evidence will be 10. 

Also consider another example: for the same statement "raven is black" system encounters 999 ravens that are black and only 1 white raven then positive evidence will be 999, negative evidence will be 1 and total evidence will be 1000. 

Truth value is a tuple rational numbers in range from 0 to 1 that is nothing but proportion of different types of evidences.

The first element of the truth value is **frequency** and the second is **confidence**



### Examples