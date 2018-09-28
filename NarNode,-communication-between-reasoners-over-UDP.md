NarNode is used to let two Nar instances communicate over UDP over the network.

It can be constructed using **NarNode(int listenPort)** (the port to listen for incoming UDP packets),
alternatively it can be constructed by using an existing Nar instance: **NarNode(Nar nar, int listenPort)**

Each NarNode has a list of 
**targets=[targetNar_1,...,targetNar_n]**
where for each **targetNar_i**, tasks above **priorityThreshold(targetNar_i)** are sent to, optionally only if **mustContainTerm(targetNar_i)** is included in the task.

To add a targetNar to the targets of a NarNode nar, simply call **nar.addRedirectionTo(TargetNar target)**
or alternatively nar.addRedirectionTo(String **targetIP**, int **targetPort**, float **taskThreshold**, Term **mustContainTerm**, boolean **sendInput**)
where

**targetIP** = the IP of the target Nar (IPv6 untested, but should work too)

**targetPort** = the target port to connect to

**taskThreshold** = the priority tasks that appear in nar must at least have to be sent to all targets

**mustContainTerm** = a term that must be contained in the task's term as subterm to be sent.
