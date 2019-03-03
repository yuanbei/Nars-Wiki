### Introduction

Beginning with OpenNARS 1.6.1, there is the possibility to code plugins for the system, which can be activated and deactivated at runtime, also they can be added multiple times with different parameters, similar like in an effects program for design. Also the plugins are entirely independent from the plugin manager (they don't need to register themselves), since the plugin manager queries the plugins and its parameters with reflection. The reason why we allow such plugins is that some narrow AI plugins might be useful for certain domains.

There are some properties plugins have to fulfill in order to be valid:

* They are not allowed to violate NAL, if plugins generate NAL statements by other NAL statements, the plugin has to apply valid NAL rules and manage the stamp correctly. For example when a planner-plugin helps the general control mechanism to generate a plan to fulfill a desired goal, the resulting plan will have the same truth-value as the general control mechanism would have created with temporal induction and the temporal chaining rule.
* If they need the system to actively call an operator in order to use the plugin (most plugins are that way), they need to provide the system with the needed usage desire evidence when loaded. The system won't use what it doesn't know that it exists. A example for a possible wiki-ask-plugin:

```
<(&/,(^wonder,$sth),(^pluginAskWiki,$sth)) =/> <(*,SELF,$sth) --> knows>>.
(&&,<#sth --> knowledge>,<(*,SELF,#sth) --> knows>)! 
```

* They shouldn't violate AIKR (Assumption of Insufficient Knowledge and Resources). For some application-specific plugins it is okay to violate it though if the entire system should really just operate in this domain.

***

### Internal Experience

Allow the system to reason about internal processes, when removed NAL9 will not be used by the system if not especially trained. NAL9 is very important for the development of consciousness. (is activated by default)

***


### Misc Plugins

- Mental Operators - Because especially NAL9 operators may come with parameters, we decided to let operators also inherit from plugin. That way mental operators can be eliminated, added and configured at runtime.

- Runtime Settings - Some runtime parameters are not important enough to be part of the main window, but may be interesting to change sometimes, so we decided to add a little plugin which is just for changing runtime parameters which don't fit into the main window.

### New Plugins

Those are plugins which didn't make it into the release anymore. They can be downloaded now, OpenNARS-1.6.1 is able to load them at runtime:

### Global Anticipation

This plugin is for accelerating the updating of temporal hypotheses by the strategy, to let all hypotheses over a certain threshold of priority directly watch the input events. When the preconditions are matched, and the predicted event happens, it gets strenghtened (temporal induction), if not, it gets weakened. (When loaded it overwrites the default strategy, which works by generating a negative event when a disappointment of a prediction happens)