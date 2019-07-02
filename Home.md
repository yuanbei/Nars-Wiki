OpenNARS is the open source implementation of [NARS](https://cis.temple.edu/~pwang/NARS-Intro.html).
The reasoner "core" of OpenNARS is under [the MIT license](https://opensource.org/licenses/MIT).

This project attempts to uniformly explain and reproduce many cognitive facilities, including reasoning, learning, planning, etc, so as to provide a _unified theory, model, and system_ for AI as a whole. The ultimate goal of this research is to build thinking machines.

What makes NARS different from conventional computer systems is its ability to _learn_ from its experience and to work with _insufficient knowledge and resources_.

This page shows the overall structure of all the wiki pages on OpenNARS, which serve as an intermediate layer between the publications (as listed in https://cis.temple.edu/~pwang/papers.html and https://phillyagiteam.github.io/Website/) and comments of the code (javadoc). The pages are linked to each other, as well as to other materials.

The pages are roughly divided into two groups, the first group provides different tours over the system, for different users and purposes; the second group systematically explains OpenNARS as currently implemented, with the pages roughly correspond to the structures of the system.

# Table of contents
## 1. Entry points
  - User guides
    * [Quick Start Guide](https://github.com/opennars/opennars/wiki/Quick-Start-Guide)
    * [Developer's Guide](https://github.com/opennars/opennars/wiki/Developers-Guide)
  - Example and demonstration
    * [Single-Step Inference Examples](https://github.com/opennars/opennars/wiki/Single-step-Inference-examples)
    * [Multi-Step Inference Examples](https://github.com/opennars/opennars/wiki/MultiStep-Examples)
    * [List of current Demos](https://github.com/opennars/opennars/wiki/List-of-current-Demos) 
    * [OpenNARS and Reinforcement Learning](https://github.com/opennars/opennars/wiki/Reinforcement-Learning)
  - Overview
    * [Glossary](https://github.com/opennars/opennars/wiki/OpenNARS-Glossary)
    * [Selected Publications](https://github.com/opennars/opennars/wiki/Publications)
    * [Selected Videos](https://github.com/opennars/opennars/wiki/Selected-Videos)

## 2. Aspects of OpenNARS
  - Language and I/O
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
    
  - Logic
    * [Non Axiomatic Logic (NAL)](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) 
    * [Basic Inference in OpenNARS](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS)
    * [Sets and set operations in OpenNARS](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS)
    * [Statements and Variables](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS)
    * [revision and choice rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)
    * [variables, examples](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS)
    * [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions)
    * [basic syllogistic rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules)
    * [Extended Boolean Functions](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS)
    * [compositional rules](https://github.com/opennars/opennars/wiki/Composition)
    * [structural rules](https://github.com/opennars/opennars/wiki/Structure)
    * [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference)
    * [procedural inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) 
    * [introspective inference](https://github.com/opennars/opennars/wiki/Introspective-Inference)
    * [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) 

  - Data structure
    * [System Memory (bag, overall structure)](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure))
    * [Concept Object: Content and Attributes](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes)
    * [Data structure for evidential basis, beliefs and goals](https://github.com/opennars/opennars/wiki/Data-structure-for-evidential-basis,-beliefs-and-goals)
    * [Narsese sentence internal representation](https://github.com/opennars/opennars/wiki/Narsese-Sentence-Internal--Representation)
    * [Type of Links: task and term links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links)
    
  - Control
    * [Inference Control](https://github.com/opennars/opennars/wiki/Inference-Control)
    * [Working Cycle and Task Management](https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)
    * [Data-driven rule choosing (rule table)](https://github.com/opennars/opennars/wiki/Data-driven-rule-choosing-(rule-table))
    * [Budget Update](https://github.com/opennars/opennars/wiki/Budget-Update)
    * [Perception](https://github.com/opennars/opennars/wiki/Perception-In-OpenNARS)
    * [Emotion and Internal experience](https://github.com/opennars/opennars/wiki/Emotion-and-Internal-experience)
    * [System parameters and configuration file](https://github.com/opennars/opennars/wiki/System-parameters-and-configuration-file)