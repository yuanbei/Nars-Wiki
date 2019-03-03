### Introduction

Beginning with OpenNARS 1.6.1, there is the possibility to code plugins for the system, which can be activated and deactivated during run-time, also plugins can be added multiple times with different parameters, similar like in an effects program for design. Plugins are entirely independent from the plugin manager (they don't need to register themselves), since the plugin manager queries the plugins and its parameters with reflection. The reason why we allow such plugins is that some narrow AI plugins might be useful for certain domains.

There are some properties a plugin has to fulfill in order to be valid in OpenNARS:

* They are not allowed to violate NAL, if plugins generate Narsese statements by other Narsese statements, the plugin has to apply valid NAL rules and manage the stamp correctly. For example when a planner-plugin helps the general control mechanism to generate a plan to fulfill a desired goal, the resulting plan will have the same truth-value as the general control mechanism would have created with temporal induction and the temporal chaining rule.
* If they need the system to actively call an operator in order to use the plugin (most plugins are that way), they need to provide the system with the needed usage desire evidence when loaded. The system won't use what it doesn't know that it exists. An example for a possible wiki-ask-plugin:

```
<(&/,(^wonder,$sth),(^pluginAskWiki,$sth)) =/> <(*,SELF,$sth) --> knows>>.
(&&,<#sth --> knowledge>,<(*,SELF,#sth) --> knows>)! 
```

* They shouldn't violate AIKR (Assumption of Insufficient Knowledge and Resources). For some application-specific plugins it is okay to violate it though if the entire system should really just operate in this domain.

***

### Misc Plugins

- Mental Operators - Because operators may come with parameters, we decided to let operators also inherit from plugin. Currently the "base" plugin is SensoryChannel that provides basic methods and operator plugins extend it. That way mental operators can be eliminated, added and configured at run-time.

- Run-time Settings - Some run-time parameters are not important enough to be part of the main window, but may be interesting to change sometimes, so we decided to add a little plugin which is just for changing run-time parameters which don't fit into the main window.

### Global Anticipation

This plugin is for accelerating the updating of temporal hypotheses by the strategy, to let all hypotheses over a certain threshold of priority directly watch the input events. When the preconditions are matched, and the predicted event happens, it gets strenghtened (temporal induction), if not, it gets weakened. (When loaded it overwrites the default strategy, which works by generating a negative event when a disappointment of a prediction happens)