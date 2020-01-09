OpenNARS is the open source implementation of [NARS](https://cis.temple.edu/~pwang/NARS-Intro.html).
The reasoner "core" of OpenNARS is under [the MIT license](https://opensource.org/licenses/MIT).

This project attempts to uniformly explain and reproduce many cognitive facilities, including reasoning, learning, planning, etc, so as to provide a _unified theory, model, and system_ for AI as a whole. The ultimate goal of this research is to build thinking machines.

What makes NARS different from conventional computer systems is its ability to _learn_ from its experience and to work with _insufficient knowledge and resources_.

This page shows the overall structure of all the wiki pages on OpenNARS, which serve as an intermediate layer between the publications (as listed in https://cis.temple.edu/~pwang/papers.html and https://phillyagiteam.github.io/Website/) and comments of the code (javadoc). The pages are linked to each other, as well as to other materials.

The pages are roughly divided into two groups, the first group provides different tours over the system, for different users and purposes; the second group systematically explains OpenNARS as currently implemented, with the pages roughly correspond to the structures of the system.

# Table of contents
## 1. Entry points
  - 1.1 User guides
    * [Quick Start Guide](https://github.com/opennars/opennars/wiki/Quick-Start-Guide)
    
  - 1.2 Example and demonstration
    * [Single-Step Inference Examples](https://github.com/opennars/opennars/wiki/Single-step-Inference-examples)
    * [Multi-Step Inference Examples](https://github.com/opennars/opennars/wiki/MultiStep-Examples)
    * [List of Current Demos](https://github.com/opennars/opennars/wiki/List-of-current-Demos) 
    * [Compared with Reinforcement Learning](https://github.com/opennars/opennars/wiki/Compared-with-Reinforcement-Learning)
  - 1.3 Overview
    * [Glossary](https://github.com/opennars/opennars/wiki/OpenNARS-Glossary)
    * [Introductory Publications](https://github.com/opennars/opennars/wiki/Introductory-Publications)
    * [Selected Videos](https://github.com/opennars/opennars/wiki/Selected-Videos)

## 2. Aspects of OpenNARS
  - 2.1 Language and I/O
    * [Narsese grammar with annotations](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format))
    * [Narsese symbol list (Publication and ASCII input)](https://github.com/opennars/opennars/wiki/Narsese-symbol-list-(ASCII-version))
    * [Term: types, format](https://github.com/opennars/opennars/wiki/Term:-types,-format)
    * [Sentence: types, format](https://github.com/opennars/opennars/wiki/Sentence:-types,-format)
    * [Built-in operator list](https://github.com/opennars/opennars/wiki/Built-in-operator-list)
    * [Truth Value: Definition and Examples](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples)
    * [Desire Value: Definition and Examples](https://github.com/opennars/opennars/wiki/Desire-Value:-Definition-and-Examples)
    * [Budget Value](https://github.com/opennars/opennars/wiki/Budget-Value)
    * [GUI explanation](https://github.com/opennars/opennars/wiki/Graphical-User-Interface)
    * [Experience file: Format and Usage](https://github.com/opennars/opennars/wiki/Experience-file:-Format-and-Usage)
    * [I/O channels](https://github.com/opennars/opennars/wiki/Input-and-Output-Channels)
    * [Inter-system communication protocol](https://github.com/opennars/opennars/wiki/NarNode,-communication-between-reasoners-over-UDP)
    * [Plugins in OpenNARS](https://github.com/opennars/opennars/wiki/Plugins)
    
  - 2.2 Logic
    * [Non Axiomatic Logic (NAL) Overview](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-the-logic-behind-OpenNARS) 
    * [Basic syllogistic rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules)
    * [Basic truth-value functions](https://github.com/opennars/opennars/wiki/Truth-Functions)
    * [Extended Boolean Functions](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS)
    * [Local rules: revision and choice](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)
    * [Sets and set operations in NAL](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-NAL)
    * [Compositional rules](https://github.com/opennars/opennars/wiki/Composition)
    * [Structural rules](https://github.com/opennars/opennars/wiki/Structural-Rules)
    * [Higher-order inference](https://github.com/opennars/opennars/wiki/Higher-order-inference)
    * [Inference with variable terms](https://github.com/opennars/opennars/wiki/Inference-with-variable-terms)
    * [Temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference)
    * [Procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) 
    * [Introspective inference](https://github.com/opennars/opennars/wiki/Introspective-Inference)
    * [Backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference) 

  - 2.3 Data structure
    * [Memory Overview](https://github.com/opennars/opennars/wiki/Memory-Overview)
    * [Concept Object: Content and Attributes](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes)
    * [Task and Belief](https://github.com/opennars/opennars/wiki/Task-and-Belief)
    * [TaskLink and TermLink](https://github.com/opennars/opennars/wiki/TaskLink-and-TermLink)

  - 2.4 Control
    * [Inference Control](https://github.com/opennars/opennars/wiki/Inference-Control)
    * [Working Cycle and Task Management](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)
    * [Data-Driven Rule Choosing](https://github.com/opennars/opennars/wiki/Data-Driven-Rule-Choosing)
    * [Budget Update](https://github.com/opennars/opennars/wiki/Budget-Update)
    * [Emotion and Internal Experience](https://github.com/opennars/opennars/wiki/Emotion-and-Internal-Experience)
    * [System Parameters and Configuration File](https://github.com/opennars/opennars/wiki/System-Parameters-and-Configuration-File)

And to study the code, see !(Code Map)[https://github.com/opennars/opennars/wiki/Code-Map]