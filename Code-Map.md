This pages serves to link the code files and their purpose to the corresponding Wiki pages with explanations.
While code comments plus code shed light on the "how" (how is it implemented?), the Wiki pages give insights about the "why" (what is the purpose / why is it needed?) 

./pom.xml - The Maven configuration file of the project, including software library dependencies, and build config.

./src/main/java/org/opennars - The main code package of the project

./src/main/java/org/opennars/control - Includes code about the control mechanism (see 2.4 Control on the Wiki main page, https://github.com/opennars/opennars/wiki)

./src/main/java/org/opennars/control/DerivationContext.java - Not conceptually important, it just stores the selected premises and the stamp with the evidental base union of both of them.

./src/main/java/org/opennars/control/GeneralInferenceControl.java - Implements the main working cycle with concept task and belief selection, then applying RuleTable on task and belief, see https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS )

./src/main/java/org/opennars/control/TemporalInferenceControl.java - Event processing to form temporal relations among events, see https://github.com/opennars/opennars/wiki/Temporal-Inference)

./src/main/java/org/opennars/control/concept - Package to implement the processing within a concept, including revision (for beliefs and goals) and question answering (between questions and beliefs, goals and beliefs, quests and goals) as described in https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)

./src/main/java/org/opennars/control/concept/ProcessAnticipation.java - When a judgment about the future is derived and then processed, it will trigger an expectation that the predicted event will indeed occur as input. If not, negative evidence for the hypotheses which led to the prediction will be generated. Else the success will be noticed by induction + revision (see https://github.com/opennars/opennars/wiki/Temporal-Inference and https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules).

./src/main/java/org/opennars/control/concept/ProcessGoal.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessJudgment.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessQuestion.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessTask.java - Processing of derived tasks (see Pre-processing in https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)

./src/main/java/org/opennars/entity - Package for the main datastructures of the system (see 2.3 Data structure in https://github.com/opennars/opennars/wiki )

./src/main/java/org/opennars/entity/BudgetValue.java - The budget value, a triple (Priority, Durability, Quality), see https://github.com/opennars/opennars/wiki/Budget-Value

./src/main/java/org/opennars/entity/Concept.java - The concept data structure summarizing questions, beliefs, goals about a term, and allowing inference with neighbours, see https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes

./src/main/java/org/opennars/entity/Item.java - Abstract class for items with budget value, from which specialized items (Concept, TaskLinks, Termlinks, Tasks) inherit from.

./src/main/java/org/opennars/entity/Sentence.java - Sentence object, including term, punctuation (either question, goal, belief, quest), truth value, and stamp, see https://github.com/opennars/opennars/wiki/Sentence:-types,-format

./src/main/java/org/opennars/entity/Stamp.java - Includes the evidenal base (evidence input id's which are not supposed to overlap!), and other metadata like the occurrence time and creation time of a sentence, see https://github.com/opennars/opennars/wiki/Stamp-In-NARS

./src/main/java/org/opennars/entity/TLink.java - General class for links from which both Tasklinks and Termlinks inherit from

./src/main/java/org/opennars/entity/Task.java - The "working items" NARS processes, which are sentences with budget value, see https://github.com/opennars/opennars/wiki/Task-and-Belief

./src/main/java/org/opennars/entity/TaskLink.java - Link structure for the sampling of tasks (see https://github.com/opennars/opennars/wiki/TaskLink-and-TermLink and for processing https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)

./src/main/java/org/opennars/entity/TermLink.java - Link structure to make the sampling of beliefs efficient (see https://github.com/opennars/opennars/wiki/TaskLink-and-TermLink and for processing https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS)

./src/main/java/org/opennars/entity/TruthValue.java - NAL truth value, see https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples 

./src/main/java/org/opennars/inference - Inference package, basically capturing NAL inference, see https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-the-logic-behind-OpenNARS

./src/main/java/org/opennars/inference/BudgetFunctions.java - To decide the importance and usefulness of data items as stored by BudgetValue, see https://github.com/opennars/opennars/wiki/Budget-Update and https://github.com/opennars/opennars/wiki/Budget-Value 

./src/main/java/org/opennars/inference/CompositionalRules.java - NAL rules which compose terms, see https://github.com/opennars/opennars/wiki/Composition

./src/main/java/org/opennars/inference/LocalRules.java - Revision, choice, question answering, see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/inference/RuleTables.java - Main inference entry point, applies all NAL rules to the task and the belief based on the term/link structure, see https://github.com/opennars/opennars/wiki/Data-Driven-Rule-Choosing

./src/main/java/org/opennars/inference/StructuralRules.java - Rules for structural transformations of terms, transforming conclusions to a different representation (such as image to product or back), see https://github.com/opennars/opennars/wiki/Structural-Rules

./src/main/java/org/opennars/inference/SyllogisticRules.java - Basic syllogistic rules inspired by Aristoteles's term logic, see https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules

./src/main/java/org/opennars/inference/TemporalRules.java - Temporal rules to establish temporal relations between events, see https://github.com/opennars/opennars/wiki/Temporal-Inference

./src/main/java/org/opennars/inference/TruthFunctions.java - NAL truth functions to decide the truth value of the conclusion by the truth value of the premises, see https://github.com/opennars/opennars/wiki/Truth-Functions

./src/main/java/org/opennars/inference/UtilityFunctions.java - Helper functions for the truth functions to extend boolean functions to continuous ones, see https://github.com/opennars/opennars/wiki/Truth-Functions

./src/main/java/org/opennars/interfaces - Self-explanatory interfaces for external usage, serves no conceptual purpose other than making code less reliant on specific implementations, hence explanations of interface files are omitted here.

./src/main/java/org/opennars/io - Package for I/O

./src/main/java/org/opennars/io/ConfigReader.java - Read config files in which parameter values and plugins to load and attach at startup can be specified.

./src/main/java/org/opennars/io/Narsese.java - The Narsese parser, parsing strings into input tasks, see https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)

./src/main/java/org/opennars/io/Parser.java - Just a convenient parser interface in case that other knowledge formats will be supported for input as well in the future.

./src/main/java/org/opennars/io/Symbols.java - The symbols used in I/O, see https://github.com/opennars/opennars/wiki/Narsese-symbol-list-(ASCII-version) and https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)

./src/main/java/org/opennars/io/Texts.java - Just convenient string processing and string representations, only helper functions, it serves no conceptual role.

./src/main/java/org/opennars/io/events - A package about events an application can listen to

./src/main/java/org/opennars/io/events/AnswerHandler.java - Listen to answers for questions

./src/main/java/org/opennars/io/events/EventEmitter.java - Allows to listen to internal reasoner events (CycleStart, ConceptSelected etc., these are not events in NARS sense but events from a reasoning engine / software perspective)

./src/main/java/org/opennars/io/events/EventHandler.java - Event handler for listening to reasoner events.

./src/main/java/org/opennars/io/events/Events.java - The internal reasoner event types.

./src/main/java/org/opennars/io/events/OutputHandler.java - General class for handling reasoner output (a subset of the software events the reasoner generates internally), such as question answers, derivations, from which TextOutputHandler inherits from.

./src/main/java/org/opennars/io/events/TextOutputHandler.java - Transforms output events into actual output to be displayed.

./src/main/java/org/opennars/language - Objects for the NAL term types, see https://github.com/opennars/opennars/wiki/Term:-types,-format and https://github.com/opennars/opennars/wiki/Narsese-symbol-list-(ASCII-version)

./src/main/java/org/opennars/language/AbstractTerm.java - Just an interface for terms in general.

./src/main/java/org/opennars/language/CompoundTerm.java - An abstract class from which all compound term objects inherit.

./src/main/java/org/opennars/language/Conjunction.java

./src/main/java/org/opennars/language/DifferenceExt.java

./src/main/java/org/opennars/language/DifferenceInt.java

./src/main/java/org/opennars/language/Disjunction.java

./src/main/java/org/opennars/language/Equivalence.java

./src/main/java/org/opennars/language/Image.java

./src/main/java/org/opennars/language/ImageExt.java

./src/main/java/org/opennars/language/ImageInt.java

./src/main/java/org/opennars/language/Implication.java

./src/main/java/org/opennars/language/Inheritance.java

./src/main/java/org/opennars/language/Instance.java

./src/main/java/org/opennars/language/InstanceProperty.java

./src/main/java/org/opennars/language/IntersectionExt.java

./src/main/java/org/opennars/language/IntersectionInt.java

./src/main/java/org/opennars/language/Interval.java

./src/main/java/org/opennars/language/Negation.java

./src/main/java/org/opennars/language/Product.java

./src/main/java/org/opennars/language/Property.java

./src/main/java/org/opennars/language/SetExt.java

./src/main/java/org/opennars/language/SetInt.java

./src/main/java/org/opennars/language/SetTensional.java - Set term abstract class, used by SetExt and SetInt.

./src/main/java/org/opennars/language/Similarity.java

./src/main/java/org/opennars/language/Statement.java

./src/main/java/org/opennars/language/Tense.java

./src/main/java/org/opennars/language/Term.java - Atomic term, the only one which isn't a CompoundTerm.

./src/main/java/org/opennars/language/Terms.java - Term utilities, such as for extracting intervals recursively.

./src/main/java/org/opennars/language/Variable.java

./src/main/java/org/opennars/language/Variables.java - Utility functions for processing terms with variables, mainly Unification algorithm and variable substitution.

./src/main/java/org/opennars/main - The main package of NARS

./src/main/java/org/opennars/main/MiscFlags.java - Some misc flags for debug and logging purposes, only relevant for developers.

./src/main/java/org/opennars/main/Nar.java - The main Nar object to use OpenNARS in an application, it supports important methods such as .addInput(Narsese string), .cycles(amount of cycles to run the reasoner), addPlugin (for registering plugins, such as operators NARS can call), addSensoryChannel, and ability to register software event handlers for question answers etc.

./src/main/java/org/opennars/main/NarNode.java - A Nar object which runs in the network, communicating to other Nar nodes and accepting inputs from other applications via UDP.

./src/main/java/org/opennars/main/Parameters.java - The system parameters

./src/main/java/org/opennars/main/Shell.java - Main shell supporting interactive usage of OpenNARS in the shell.

./src/main/java/org/opennars/operator - A package for all operators the system can call.

./src/main/java/org/opennars/operator/FunctionOperator.java - For operators which return a single value, like ^add.

./src/main/java/org/opennars/operator/ImaginationSpace.java - An "imaginary"/mental context which groups perceptive terms with values and operators on the same space type (like zooming in visual space and the zoom value, filtering in audio space and filter values, ops regarding some mental internal playground or internal map etc.), these operators usually generate events with new perceptive terms (which are terms with a non-null ImaginationSpace attached). This is experimental and was first introduced for the vision channel, to support its perceptive terms. For instance VisualSpace inherits from it.

./src/main/java/org/opennars/operator/NullOperator.java - An operator which has no effect, it's only used for examples and testing, to see whether the system calls the right operators in certain examples.

./src/main/java/org/opennars/operator/Operation.java And inheritance with the format ```<(*,{SELF},arg1,...,argn) --> ^Operator>```, which has both an operator and the arguments the operator should be called with.

./src/main/java/org/opennars/operator/Operator.java - Operators NARS can call to interact with "whatever" (change motor speed in a robot, generate user message, change paramters of own internal resource allocation etc.). Encoded as an atomic term starting with ^, associated with a Java procedure which can be invoked.

./src/main/java/org/opennars/operator/mental - Mental operators, operators which consequences appear directly within the system, a NAL-9 construct, see https://github.com/opennars/opennars/wiki/Introspective-Inference and https://github.com/opennars/opennars/wiki/Built-in-operator-list 

./src/main/java/org/opennars/operator/mental/Anticipate.java - Anticipating outcomes as a mental operator, see https://github.com/opennars/opennars/wiki/Introspective-Inference

./src/main/java/org/opennars/operator/mental/Believe.java - The system anually changing its own belief

./src/main/java/org/opennars/operator/mental/Consider.java - The system manually processing a concept

./src/main/java/org/opennars/operator/mental/Doubt.java - The system manually reducing its confidence about a belief

./src/main/java/org/opennars/operator/mental/Evaluate.java - The system asking itself a question about the desire of a goal, this kind of question we call quest.

./src/main/java/org/opennars/operator/mental/Feel.java - Abstract class for the system actively querying internal values.
./src/main/java/org/opennars/operator/mental/FeelBusy.java - The system querying its busyiness in terms of average priority of recently processed tasks.

./src/main/java/org/opennars/operator/mental/FeelSatisfied.java - The system querying its state of satisfaction

./src/main/java/org/opennars/operator/mental/Hesitate.java - The system reducing the confidence of a goal

./src/main/java/org/opennars/operator/mental/Name.java - Giving a name to a term

./src/main/java/org/opennars/operator/mental/Register.java - An operator to register an operator at runtime

./src/main/java/org/opennars/operator/mental/Remind.java - The system manually increasing the priority of a concept

./src/main/java/org/opennars/operator/mental/Want.java - The system manually creating a goal

./src/main/java/org/opennars/operator/mental/Wonder.java - The system manually generating a question

./src/main/java/org/opennars/operator/misc - A package for misc operators

./src/main/java/org/opennars/operator/misc/Add.java - An operator allowing the system to add numbers, it's like an internal "pocket calculator"

./src/main/java/org/opennars/operator/misc/Count.java - An operator to let the system count the cardinality of sets.

./src/main/java/org/opennars/operator/misc/Reflect.java - An operator to let the system reflect on the structure of compound terms.

./src/main/java/org/opennars/operator/misc/System.java - An operator to call a tool available in the Shell/OS environment

./src/main/java/org/opennars/plugin - A package for adding plugins to OpenNARS.

./src/main/java/org/opennars/plugin/Plugin.java - Plugins like operators, sensory channels, knowledge base connections, system monitors etc.

./src/main/java/org/opennars/plugin/mental - Plugins affecting the internal processing of the system. Note: while operators are also plugins, plugins can consist of multiple operators, and can be sensory channels as well.

./src/main/java/org/opennars/plugin/mental/Abbreviation.java - A plugin which allows the system to simplify terms

./src/main/java/org/opennars/plugin/mental/ComplexEmotions.java - A plugin for self-regulation investigations.

./src/main/java/org/opennars/plugin/mental/Counting.java - A plugin allowing the system to count quantities.

./src/main/java/org/opennars/plugin/mental/Emotions.java - A plugin which introduces internal measurements to OpenNARS, such as Busyness, Satisfaction, which are for self-monitoring and self-control, NAL-9.

./src/main/java/org/opennars/plugin/mental/InternalExperience.java - A plugin which listens to reasoner events and generates internal experience, allowing the system to reflect on what it is believing, thinking, wanting etc.

./src/main/java/org/opennars/plugin/perception - Plugins for perception purposes

./src/main/java/org/opennars/plugin/perception/SensoryChannel.java - Abstract class, a class to create plugins for sensor-related processing.

./src/main/java/org/opennars/plugin/perception/VisionChannel.java - A vision channel using a prototype-based approach for unsupervised pattern learning and recognition, uses NAL revision, and generates NARS events to be fed into the reasoner. See perception from an AGI perspective https://cis.temple.edu/~pwang/Publication/perception.pdf

./src/main/java/org/opennars/plugin/perception/VisualSpace.java - Used to support sensory terms, terms with 2D truth value, and perceptive terms (with zooming, position etc. parameters additionally), as well as the corresponding operators, as described in https://cis.temple.edu/~pwang/Publication/perception.pdf

./src/main/java/org/opennars/storage - A package for the system's memory

./src/main/java/org/opennars/storage/Bag.java - The Bag datastructure for implementing Attention by sampling items with chance correlated with their priority, see Bag Data Structure in https://github.com/opennars/opennars/wiki/Memory-Overview and https://github.com/opennars/opennars/wiki/Inference-Control-and-Memory-Structure#memory-structure-and-control-strategy

./src/main/java/org/opennars/storage/Distributor.java - Sampling structure deciding the amount of "selections" in each level, essentially the sampling distribution, so that higher levels will have more and thus the items in them a higher access frequency.

./src/main/java/org/opennars/storage/Memory.java - The memory implementation, in which the concepts "live", and the tasks and beliefs. See https://github.com/opennars/opennars/wiki/Memory-Overview and https://github.com/opennars/opennars/wiki/Inference-Control-and-Memory-Structure

./src/main/java/org/opennars/util - Just misc utilities

./src/main/java/org/opennars/util/ListUtil.java - Useful Java8 "extension" for lists.
