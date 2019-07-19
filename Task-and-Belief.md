A Narsese [sentence](https://github.com/opennars/opennars/wiki/Sentence:-types,-format) is stored in memory as either a _task_ or a _belief_ (or both). Roughly speaking, a _task_ is what to be processed by the system:
* A _judgment_ needs to be absorbed into the beliefs.
* A _goal_ needs to be achieved by the operations.
* A _question_ or _query_ needs to be answered by the matching judgments or goals.
On the other hand, a _belief_ is a judgment that has been absorbed already and will be used to process the tasks. While tasks are active and define the current context, while beliefs are passively used as background knowledge. Between the two types, the number of tasks is relatively small, while the number of beliefs is much larger. 

For example, when a piece of new information _<raven --> [black]>._ enters the system, it is initially taken as a task, which will create or revise beliefs, generate implications via spontaneous forward inference, solve pending goals or questions, etc. Then the task will be gradually forgotten, and the information will remain as a belief for a long time.

The diagram below shows a sentence within an input task:
![Sentence_in_memory](https://user-images.githubusercontent.com/24262360/54455892-37685780-4733-11e9-839f-fd35dfea69ef.png)

