NarNode is used to let two Nar instances communicate over UDP. This allows multiple Nar instances to exchange useful knowledge over the network, which can especially be fruitful when multiple Nar instances work on similar problems.
In such cases, the learning speed can be extremely accelerated, because when one Nar agent has to deal with a new case, it might be a case another Nar already had to deal with. This is even more likely when more agents are involved. 

# Creating a NarNode instance
A NarNode instance can be created using **NarNode(int listenPort)** (the port to listen for incoming UDP packets),
alternatively it can be constructed by using an existing Nar instance: **NarNode(Nar nar, int listenPort)**

# How NarNodes communicate
Each NarNode has a list of 
**targets=[targetNar_1,...,targetNar_n]**
where for each **targetNar_i**, tasks above **priorityThreshold(targetNar_i)** are sent to, optionally only if **mustContainTerm(targetNar_i)** is included in the task.
The sent task gets then processed in each **targetNar_i** as if it would be a derived task of itself.

# How to specify NarNodes targets
To add a targetNar to the targets of a NarNode nar, we simply call ****nar.addRedirectionTo**(TargetNar target)**
or alternatively **nar.addRedirectionTo**(String **targetIP**, int **targetPort**, float **taskThreshold**, Term **mustContainTerm**, boolean **sendInput**)
where

**targetIP** = the IP of the target Nar (IPv6 untested, but should work too)

**targetPort** = the target port to connect to

**taskThreshold** = the priority tasks that appear in nar must at least have to be sent to all targets

**mustContainTerm** = a term that must be contained in the task's term as subterm to be sent.

# Sending Narsese input

It is also possible to send Narsese string input to a NarNode without using a NarNode.
For this purpose, there is a static function in NarNode:
**void sendNarsese**(String **input**, TargetNar **target**)
Additionally, consistently as for addRedirectionTo, there is an alternative:
**sendNarsese**(String **input**, String **targetIP**, int **targetPort**, float **taskThreshold**, Term **mustContainTerm**)

# Code example
One full code example can be seen in our NarNode test: https://github.com/opennars/opennars/blob/master/src/test/java/org/opennars/core/NarNodeTest.java#L46

# Used protocol
Currently, **sendNarsese** sends a serialized String object, and the tasks are transferred as serialized Task objects,
each of which is assumed to fit into a single UDP packet. 

#Protocol limitations
We are aware that is not very convenient to use the Java's object serialization protocol from native code using JNI, and although it is possible to do so without running a JVM,
it might be easier to use existing UNIX tools to pipe text sent over network into the standard IO of one of the NarNodes within the network. In the future we might improve the protocol so that char byte sequences, as can be easily generated in C/C++, will also be usable by the NarNode to be received within a UDP packet as Narsese input.



# Questions

Why do we not just send Narsese between Nar nodes, why are entire tasks sent?

NarNode is designed to work in any possible configuration of nodes, involving cycles,
in simplest case NarNode **A** sends to NarNode **B**, and NarNode **B** send to **A**.
In such cases, cyclic reasoning can become a potential issue, that is, if **A** believes **x. {1}** and **<x ==> y>. {2}** and **B** believes **<y ==> x>. {3}**, **x.** could be derived by deriving **y. {1,2}**  in NarNode **A**, and sending to to NarNode **B**, which can then derive **x. {1,2,3}** and send it over to **A**. If **A** wouldn't know the evidental base, it would revise the derived task **x. {1,2,3}** with the **x. {1}** it started with, becoming more and more confident about **x** just by doing the same derivations again and again, clearly we don't want that.
Another reason: Sending the task also makes it keep track of occurrence time of derived tasks for time-critical applications.

Why UDP?
The TCP overhead is not required, should a packet be lost, re-derivation will re-deliver it anyway. Also, there is no need for derived tasks to be received in the order they were derived.
