### Introduction

Experience file is a simple text file, it is an optional feature of OpenNARS that holds complete experience from the system until certain point including input, inferences, Narsese statements etc.  It can be viewed as a system snapshot from the time when user indicated to start recording an experience until the termination of a reasoning system 

Recording an experience of a system is necessary for multiple reasons:

1. The system may be stopped at some time and resumed at a later time, loading experience file allows system to start reasoning process from the point when it was stopped earlier

2. There might be multiple OpenNARS systems (Nar-Nodes) and exchanging of experience might be useful

3. Using an experience file system can recreate entire chain of derivation that is helpful for explaining and tracking any derivation

### Explanation

Experience file is nothing but text file, below is a sample experience file

![experience_image_1](https://user-images.githubusercontent.com/24262360/52545458-ac87ec00-2d85-11e9-90de-8b2f18da6e4a.png)

Each line starts with "IN" or "OUT" indication whether Narsese statement is input to the system or derivation (output).
as we can only two inputs were given to the system, the rest are derivations

We can see that in addition to Narsese statement with truth values there is other experience information attached between curly braces {}.

The first integer is simply a step number showing at what step this sentence appeared (starts with 0).  For above example the first step was an input statement <{tim} --> cat>. 

After column ":" there are one or more tuples showing id of a reasoner and an integer showing from each input the statement was derived. Reasoner id is useful when there are more than one reasoner in case of network exchange or if experience was resumed at a different instance of a system. For example look at line 14 in the experience file:<br/>
OUT: <{garfield,tim} --> cat>. %1.00;0.81% {30 : (-7370839197512280216,1);(-7370839197512280216,0)}<br/>
Here the integer is 30 means that on step 30th the sentence <{garfield,tim} --> cat>. %1.00;0.81% was derived.
The first tuple "(-7370839197512280216,1)" shows that reasoner id is "-7370839197512280216" and the sentence was derived from input 1, the second tuple shows that the sentence was derived also from input 2 by the same reasoner, id is "-7370839197512280216".


