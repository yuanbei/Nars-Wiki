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

./src/main/java/org/opennars/io/Symbols.java - The symbols used in I/O, see https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)

./src/main/java/org/opennars/io/Texts.java - Just convenient string processing and string representations, only helper functions, it serves no conceptual role.

./src/main/java/org/opennars/io/events - A package about events an application can listen to

./src/main/java/org/opennars/io/events/AnswerHandler.java - Listen to answers for questions

./src/main/java/org/opennars/io/events/EventEmitter.java - Allows to listen to internal reasoner events (CycleStart, ConceptSelected etc., these are not events in NARS sense but events from a reasoning engine / software perspective)

./src/main/java/org/opennars/io/events/EventHandler.java - Event handler for listening to reasoner events.

./src/main/java/org/opennars/io/events/Events.java - The internal reasoner event types.

./src/main/java/org/opennars/io/events/OutputHandler.java - General class for handling reasoner output (a subset of the software events the reasoner generates internally), such as question answers, derivations, from which TextOutputHandler inherits from.

./src/main/java/org/opennars/io/events/TextOutputHandler.java - Transforms output events into actual output to be displayed.

./src/main/java/org/opennars/language
./src/main/java/org/opennars/language/AbstractTerm.java
./src/main/java/org/opennars/language/CompoundTerm.java
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
./src/main/java/org/opennars/language/SetTensional.java
./src/main/java/org/opennars/language/Similarity.java
./src/main/java/org/opennars/language/Statement.java
./src/main/java/org/opennars/language/Tense.java
./src/main/java/org/opennars/language/Term.java
./src/main/java/org/opennars/language/Terms.java
./src/main/java/org/opennars/language/Variable.java
./src/main/java/org/opennars/language/Variables.java
./src/main/java/org/opennars/language/package-info.java
./src/main/java/org/opennars/main
./src/main/java/org/opennars/main/MiscFlags.java
./src/main/java/org/opennars/main/Nar.java
./src/main/java/org/opennars/main/NarNode.java
./src/main/java/org/opennars/main/Parameters.java
./src/main/java/org/opennars/main/Shell.java
./src/main/java/org/opennars/main/overview.html
./src/main/java/org/opennars/main/ParseTest.java
./src/main/java/org/opennars/operator
./src/main/java/org/opennars/operator/FunctionOperator.java
./src/main/java/org/opennars/operator/ImaginationSpace.java
./src/main/java/org/opennars/operator/NullOperator.java
./src/main/java/org/opennars/operator/Operation.java
./src/main/java/org/opennars/operator/Operator.java
./src/main/java/org/opennars/operator/mental
./src/main/java/org/opennars/operator/mental/Anticipate.java
./src/main/java/org/opennars/operator/mental/Believe.java
./src/main/java/org/opennars/operator/mental/Consider.java
./src/main/java/org/opennars/operator/mental/Doubt.java
./src/main/java/org/opennars/operator/mental/Evaluate.java
./src/main/java/org/opennars/operator/mental/Feel.java
./src/main/java/org/opennars/operator/mental/FeelBusy.java
./src/main/java/org/opennars/operator/mental/FeelSatisfied.java
./src/main/java/org/opennars/operator/mental/Hesitate.java
./src/main/java/org/opennars/operator/mental/Name.java
./src/main/java/org/opennars/operator/mental/Register.java
./src/main/java/org/opennars/operator/mental/Remind.java
./src/main/java/org/opennars/operator/mental/Want.java
./src/main/java/org/opennars/operator/mental/Wonder.java
./src/main/java/org/opennars/operator/misc
./src/main/java/org/opennars/operator/misc/Add.java
./src/main/java/org/opennars/operator/misc/Count.java
./src/main/java/org/opennars/operator/misc/Reflect.java
./src/main/java/org/opennars/operator/misc/System.java
./src/main/java/org/opennars/plugin
./src/main/java/org/opennars/plugin/Plugin.java
./src/main/java/org/opennars/plugin/mental
./src/main/java/org/opennars/plugin/mental/Abbreviation.java
./src/main/java/org/opennars/plugin/mental/ComplexEmotions.java
./src/main/java/org/opennars/plugin/mental/Counting.java
./src/main/java/org/opennars/plugin/mental/Emotions.java
./src/main/java/org/opennars/plugin/mental/InternalExperience.java
./src/main/java/org/opennars/plugin/perception
./src/main/java/org/opennars/plugin/perception/SensoryChannel.java
./src/main/java/org/opennars/plugin/perception/VisionChannel.java
./src/main/java/org/opennars/plugin/perception/VisualSpace.java
./src/main/java/org/opennars/storage
./src/main/java/org/opennars/storage/Bag.java
./src/main/java/org/opennars/storage/Distributor.java
./src/main/java/org/opennars/storage/Memory.java
./src/main/java/org/opennars/storage/package-info.java
./src/main/java/org/opennars/util
./src/main/java/org/opennars/util/ListUtil.java
