This pages serves to link the code files and their purpose to the corresponding Wiki pages with explanations.
While code comments plus code shed light on the "how" (how is it implemented?), the Wiki pages give insights about the "why" (what is the purpose / why is it needed?) 

./pom.xml - The Maven configuration file of the project, including software library dependencies, and build config.

./src/main/java/org/opennars - The main code package of the project

./src/main/java/org/opennars/control - Includes code about the control mechanism (see 2.4 at the Wiki main page, https://github.com/opennars/opennars/wiki)
./src/main/java/org/opennars/control/DerivationContext.java - Not conceptually important, it just stores the selected premises and the stamp with the evidental base union of both of them.

./src/main/java/org/opennars/control/GeneralInferenceControl.java - Implements the main working cycle with concept task and belief selection, then applying RuleTable on task and belief, see https://github.com/opennars/opennars/wiki/Working-Cycle-and-Tasks-Management-in-OpenNARS )

./src/main/java/org/opennars/control/TemporalInferenceControl.java - Event processing to form temporal relations among events, see https://github.com/opennars/opennars/wiki/Temporal-Inference)

./src/main/java/org/opennars/control/concept - Package to implement the processing within a concept, including revision (for beliefs and goals) and question answering (between questions and beliefs, goals and beliefs, quests and goals) as described in https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)

./src/main/java/org/opennars/control/concept/ProcessAnticipation.java - When a judgment about the future is derived and then processed, it will trigger an expectation that the predicted event will indeed occur as input. If not, negative evidence for the hypotheses which led to the prediction will be generated. Else the success will be noticed by induction + revision.

./src/main/java/org/opennars/control/concept/ProcessGoal.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessJudgment.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessQuestion.java - see https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules

./src/main/java/org/opennars/control/concept/ProcessTask.java - Processing of derived tasks

./src/main/java/org/opennars/entity
./src/main/java/org/opennars/entity/BudgetValue.java
./src/main/java/org/opennars/entity/Concept.java
./src/main/java/org/opennars/entity/Item.java
./src/main/java/org/opennars/entity/Sentence.java
./src/main/java/org/opennars/entity/Stamp.java
./src/main/java/org/opennars/entity/TLink.java
./src/main/java/org/opennars/entity/Task.java
./src/main/java/org/opennars/entity/TaskLink.java
./src/main/java/org/opennars/entity/TermLink.java
./src/main/java/org/opennars/entity/TruthValue.java
./src/main/java/org/opennars/entity/package-info.java
./src/main/java/org/opennars/inference
./src/main/java/org/opennars/inference/BudgetFunctions.java
./src/main/java/org/opennars/inference/CompositionalRules.java
./src/main/java/org/opennars/inference/LocalRules.java
./src/main/java/org/opennars/inference/RuleTables.java
./src/main/java/org/opennars/inference/StructuralRules.java
./src/main/java/org/opennars/inference/SyllogisticRules.java
./src/main/java/org/opennars/inference/TemporalRules.java
./src/main/java/org/opennars/inference/TruthFunctions.java
./src/main/java/org/opennars/inference/UtilityFunctions.java
./src/main/java/org/opennars/inference/package-info.java
./src/main/java/org/opennars/interfaces
./src/main/java/org/opennars/interfaces/Eventable.java
./src/main/java/org/opennars/interfaces/InputFileConsumer.java
./src/main/java/org/opennars/interfaces/Multistepable.java
./src/main/java/org/opennars/interfaces/NarseseConsumer.java
./src/main/java/org/opennars/interfaces/Pluggable.java
./src/main/java/org/opennars/interfaces/Resettable.java
./src/main/java/org/opennars/interfaces/SensoryChannelConsumer.java
./src/main/java/org/opennars/interfaces/TaskConsumer.java
./src/main/java/org/opennars/interfaces/Timable.java
./src/main/java/org/opennars/interfaces/pub
./src/main/java/org/opennars/interfaces/pub/Reasoner.java
./src/main/java/org/opennars/io
./src/main/java/org/opennars/io/ConfigReader.java
./src/main/java/org/opennars/io/Narsese.java
./src/main/java/org/opennars/io/Parser.java
./src/main/java/org/opennars/io/Symbols.java
./src/main/java/org/opennars/io/Texts.java
./src/main/java/org/opennars/io/events
./src/main/java/org/opennars/io/events/AnswerHandler.java
./src/main/java/org/opennars/io/events/EventEmitter.java
./src/main/java/org/opennars/io/events/EventHandler.java
./src/main/java/org/opennars/io/events/Events.java
./src/main/java/org/opennars/io/events/OutputHandler.java
./src/main/java/org/opennars/io/events/TextOutputHandler.java
./src/main/java/org/opennars/io/package-info.java
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
