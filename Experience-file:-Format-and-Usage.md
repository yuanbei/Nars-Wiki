### Introduction

Experience file is a simple text file, it is an optional feature of OpenNARS that holds complete experience from the system until certain point including input, inferences, Narsese statements etc.  It can be viewed as a system snapshot from the time when user indicated to start recording an experience until the termination of a reasoning system 

Recording an experience of a system is necessary for multiple reasons:

1. The system may be stopped at some time and resumed at a later time, loading experience file allows system to start reasoning process from the point when it was stopped earlier

2. There might be multiple OpenNARS systems (Nar-Nodes) and exchanging of experience might be useful

3. Using an experience file system can recreate entire chain of derivation that is helpful for explaining and tracking any derivation

### Explanation

Experience file is nothing but text file look below for an example
IN: <{tim} --> cat>. %1.00;0.90% {0 : (-7370839197512280216,0)} 
OUT: <{tim} --> cat>. %1.00;0.90% {0 : (-7370839197512280216,0)} 
OUT: (--,<{tim} --> cat>). %0.00;0.90% {4 : (-7370839197512280216,0)} 
OUT: (--,<{tim} --> cat>). %0.00;0.90% {4 : (-7370839197512280216,0)} 
OUT: (--,<{tim} --> cat>). %0.00;0.90% {4 : (-7370839197512280216,0)} 
OUT: <{tim} --> cat>. %1.00;0.90% {11 : (-7370839197512280216,0)} 
OUT: <{tim} --> cat>. %1.00;0.90% {11 : (-7370839197512280216,0)} 
OUT: <{tim} --> cat>. %1.00;0.90% {11 : (-7370839197512280216,0)} 
IN: <{garfield} --> cat>. %1.00;0.90% {28 : (-7370839197512280216,1)} 
OUT: <{garfield} --> cat>. %1.00;0.90% {28 : (-7370839197512280216,1)} 
OUT: <{tim} --> {garfield}>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <{garfield} --> {tim}>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <{garfield} <-> {tim}>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <{garfield,tim} --> cat>. %1.00;0.81% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <<{tim} --> $1> ==> <{garfield} --> $1>>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <<{garfield} --> $1> ==> <{tim} --> $1>>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: <<{garfield} --> $1> <=> <{tim} --> $1>>. %1.00;0.45% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: (&&,<{garfield} --> #1>,<{tim} --> #1>). %1.00;0.81% {30 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: (--,<{garfield} --> cat>). %0.00;0.90% {31 : (-7370839197512280216,1)} 
OUT: (--,<{garfield} --> cat>). %0.00;0.90% {31 : (-7370839197512280216,1)} 
OUT: (--,<{garfield} --> cat>). %0.00;0.90% {31 : (-7370839197512280216,1)} 
OUT: (--,<{garfield,tim} --> cat>). %0.00;0.81% {33 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: (--,<{garfield,tim} --> cat>). %0.00;0.81% {33 : (-7370839197512280216,1);(-7370839197512280216,0)} 
OUT: (--,<{garfield,tim} --> cat>). %0.00;0.81% {33 : (-7370839197512280216,1);(-7370839197512280216,0)} 














