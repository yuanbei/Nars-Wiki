OpenNARS, especially its [control mechanism](https://github.com/opennars/opennars/wiki/Inference-Control), is specified with many "system parameters", which are quantities may take different values in separate copies of the model. It is the case either because the best value has not been found, or (more often) because there is no "best value". As the development advances, the former cases will be gradually eliminated, while the latter cases will remain.

A system parameter indicates a bias of the system, so different values will give the system different "personalities". There is no best value because a certain personality may be good for solving some problems, but bad for some others. Even though usually there is a "normal range" for each parameter, and values outside it will cause serious problems.

One way to tune and study system parameters is to compare them in a community of multiple OpenNARS implementations, each with a different personality. It is also possible to use an evolutionary process to generate and select new personalities.

System parameters are defined in **org.main.parameters.java**. It is also possible to define them in a config XML file and feed file to the system at the initial stage. Below is a list of parameters with brief descriptions:

**NOVELTY_HORIZON = 100000**: After a term-link is used on a task, it won't be used on the task again in a period specified by this parameter<br/>

**CONCEPT_BAG_SIZE = 10000**: The size of the (only) concept bag. It specifies the maximum number of concepts in the memory<br/>

**DECISION_THRESHOLD = 0.51f**: Minimum expectation for a desire value to execute an operation<br/>

**DURATION = 5**:Cycles per duration. If the current time (by the internal clock) is T, then he range of "now" is [T - DURATION/2, T + DURATION/2]<br/>

**HORIZON = 1**: Evidential Horizon, the amount of future evidence to be compared with the available evidence when calculating confidence<br/>

**TRUTH_EPSILON = 0.01 and BUDGET_EPSILON = 0.0001**: The internal precision used for TruthValue calculations. Value of 0.01 gives 100 truth value states between 0 and 1.0. Other values may be used, for example, 0.02 for 50, 0.10 for 10, etc.<br/>

**BUDGET_THRESHOLD = 0.01**:The budget threshold rate for task to be accepted<br/>

**DEFAULT_CONFIRMATION_EXPECTATION = 0.6**: Default expectation for confirmation on anticipation<br/>

**ALWAYS_CREATE_CONCEPT = true**: Ignore expectation for creation of concept<br/>

**DEFAULT_CREATION_EXPECTATION = 0.66**: Default expectation for creation of concept<br/>

**DEFAULT_CREATION_EXPECTATION_GOAL = 0.6**: Default expectation for creation of concept for goals<br/>

**DEFAULT_JUDGMENT_CONFIDENCE = 0.9**: Default confidence of input judgment<br/> 

**DEFAULT_JUDGMENT_PRIORITY = 0.8**: Default priority of input judgment<br/>

**DEFAULT_JUDGMENT_DURABILITY = 0.5**: Default durability of input judgment<br/>

**DEFAULT_QUESTION_PRIORITY = 0.9**: Default priority of input question<br/>

**DEFAULT_QUESTION_DURABILITY = 0.9**: Default durability of input question<br/>

**DEFAULT_GOAL_CONFIDENCE = 0.9**: Default confidence of input goal<br/>

**DEFAULT_GOAL_PRIORITY = 0.9**: Default priority of input goal<br/>

**DEFAULT_GOAL_DURABILITY = 0.9**: Default durability of input goal<br/>

**DEFAULT_QUEST_PRIORITY = 0.9**: Default priority of input quest<br/>

**DEFAULT_QUEST_DURABILITY = 0.9**: Default durability of input quest<br/>

**TASK_LINK_BAG_SIZE = 2000**: Size of Task-Link Bag<br/>

**TERM_LINK_BAG_SIZE = 1000**: Size of Term-Link Bag<br/>

**TERM_LINK_MAX_MATCHED = 10**: Maximum TermLinks checked for novelty for each TaskLink in TermLinkBag<br/>

**NOVEL_TASK_BAG_SIZE = 1000**: Size of Novel Task Buffer<br/>

**SEQUENCE_BAG_SIZE = 300**: Size of derived sequence and input event bag<br/>

**OPERATION_BAG_SIZE = 10**: Size of remembered last operation tasks<br/>

**PROJECTION_DECAY = 0.1**: How fast events decay in confidence<br/>

**MAXIMUM_EVIDENTAL_BASE_LENGTH = 2000**: Maximum length of the evidential base of the Stamp, a power of 2<br/>

**TERMLINK_MAX_REASONED = 3**: Maximum TermLinks used in reasoning for each Task in Concept<br/>

**TERM_LINK_RECORD_LENGTH =10**: Record-length for newly created TermLink's<br/>

**CONCEPT_BELIEFS_MAX = 28**: Maximum number of beliefs kept in a Concept<br/>

**CONCEPT_QUESTIONS_MAX = 5**: Maximum number of questions kept in a Concept<br/>

**CONCEPT_GOALS_MAX = 7**: Maximum number of goals kept in a Concept<br/>

**reliance = 0.9**: Reliance factor, the empirical confidence of analytical truth. The same as default confidence<br/>

**DISCOUNT_RATE = 0.5**: The rate of confidence decrease in mental operations Doubt and Hesitate set to zero to disable this feature<br/>

**IMMEDIATE_ETERNALIZATION=true**: whether eternalization should happen on every derivation<br/>

**CURIOSITY_DESIRE_CONFIDENCE_MUL = 0.1**: how much risk is the system allowed to take just to fulfill its hunger for knowledge? <br/>

**CURIOSITY_DESIRE_PRIORITY_MUL = 0.1**: how much priority should curiosity have?<br/>

**CURIOSITY_DESIRE_DURABILITY_MUL = 0.3**: how much durability should curiosity have?<br/>

**DEFAULT_FEEDBACK_PRIORITY = 0.9**: Default priority of execution feedback<br/>

**DEFAULT_FEEDBACK_DURABILITY = 0.5**: Default durability of execution feedback<br/>

**CONCEPT_FORGET_DURATIONS = 2.0**: Concept decay rate in ConceptBag, in [1, 99].  originally: CONCEPT_FORGETTING_CYCLE How many cycles it takes an item to decay completely to a threshold value (ex: 0.1). Lower means faster rate of decay.<br/>

**TERMLINK_FORGET_DURATIONS = 10.0**: TermLink decay rate in TermLinkBag, in [1, 99]. originally: TERM_LINK_FORGETTING_CYCLE<br/>

**TASKLINK_FORGET_DURATIONS = 4.0**: TaskLink decay rate in TaskLinkBag, in [1, 99]. originally: TASK_LINK_FORGETTING_CYCLE<br/>

**EVENT_FORGET_DURATIONS = 4.0**: Sequence bag forget durations<br/>

**VARIABLE_INTRODUCTION_COMBINATIONS_MAX = 8**: Maximum attempted combinations in variable introduction.<br/>

**ANTICIPATIONS_PER_CONCEPT_MAX = 8**: Maximum anticipations about its content stored in a concept<br/>

**THREADS_AMOUNT = 1**: Default threads amount at startup<br/>

**VOLUME = 0**: Default volume at startup<br/> 

**MILLISECONDS_PER_STEP = 0**: Default miliseconds per step at startup<br/>

**STEPS_CLOCK = true**: Timing mode, steps or real time<br/>
