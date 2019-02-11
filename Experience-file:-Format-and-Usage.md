### Introduction

Experience file is a simple text file, it is an optional feature of OpenNARS that holds complete experience from the system until certain point including input, inferences, Narsese statements etc.  It can be viewed as a system snapshot from the time when user indicated to start recording an experience until the termination of a reasoning system 

Recording an experience of a system is necessary for multiple reasons:

1. The system may be stopped at some time and resumed at a later time, loading experience file allows system to start reasoning process from the point when it was stopped earlier

2. There might be multiple OpenNARS systems (Nar-Nodes) and exchanging of experience might be useful

3. Using an experience file system can recreate entire chain of derivation that is helpful for explaining and tracking any derivation

### Explanation

Experience file is nothing but text file look below for an example
![ex](https://user-images.githubusercontent.com/24262360/52545458-ac87ec00-2d85-11e9-90de-8b2f18da6e4a.png)