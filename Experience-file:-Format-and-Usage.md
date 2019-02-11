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
as we can only two inputs were given to the system, the rest is derivations

Inputs:

IN: <{tim} --> cat>. %1.00;0.90% {0 : (-7370839197512280216,0)}<br/>
IN: <{garfield} --> cat>. %1.00;0.90% {28 : (-7370839197512280216,1)} 

Sample outputs:

OUT: (--,<{tim} --> cat>). %0.00;0.90% {4 : (-7370839197512280216,0)}<br/>
OUT: <{garfield} <-> {tim}>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)}

We can see the Narsese statement with truth values and other information attached between curly braces {}
the first element is the step number. The first sentence in the whole system

