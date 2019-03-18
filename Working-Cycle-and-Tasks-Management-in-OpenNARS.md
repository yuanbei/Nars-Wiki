# Working Cycle

OpenNars runs by repeating the following working cycle:
1. Probabilistically select a concept C from the memory

2. Probabilistically select a tasklink from C, which specifies the task T to be used

3. Probabilistically select a termlink from C, which specifies the belief B to be used

4. With T and B as premises, trigger the applicable inference rules to derive new tasks and add them into the task buffer

5. Probabilistically select some tasks from the task buffer for pre-processing

Pre-processing of a task means to puts it into the corresponding concepts (and create them if they do not exist). Within a concept, the new task may create new belief, revise existing beliefs, satisfy a goal, or answer a question. If an input question obtains a best-so-far answer, it will be reported.

**Issue:** It may be necessary to add task buffers to each concept to hold the tasks added, so as to postpone their preprocessing until the concept is selected. Competition can be added into the buffer, so only selected tasks are processed.

The system's working cycle follow a fixed algorithm, and takes a small constant time to finish. The processing of a task is carried out by a number of working cycles, though their number and order are not predetermined, but decided by the control mechanism at the run time.
