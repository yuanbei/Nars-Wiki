OpenNARS is the open-source implementation of NARS (Non-Axiomatic Reasoning System), while NARS is based on NAL (Non-Axiomatic Logic).

Conceptually, NAL is defined hierarchically with multiple layers, each of them extends the logic by introducing new grammar rules and inference rules, so as to make the logic more and more powerful in its expressing and inferencing capability. For educational purpose, it is suggested to learn the system in this order. However, the separation of the layers are ignored in implementation, so in the code, the rules in each layer cannot be clearly distinguished from each other. 

The complete NAL grammar is specified in the [grammar page](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), while the inference rules are described in multiple pages, with their truth functions summarized in the [truth-value function page](https://github.com/opennars/opennars/wiki/Truth-Functions). 

In the current design, NAL consists of 9 layers in 4 groups, in the sense that it is possible to only implement one group plus the layer below it to get a functional system with well-defined capability.

## [1] Basic Inference
The simplest non-axiomatic logic, with atomic terms and single copula.

### NAL-1
NAL-1 is a logical core of NAL. The statements in it are all _inheritance_ statements with an atomic _subject_ and an atomic _predicate_. The meaning of a term is defined as its _extension_ and _intension_. The truth value of a statement consists of a _frequency_ value and a _confidence_ value. The inference rules include local rules (_revision_ and _choice_), forward syllogism (_deduction, induction, abduction_), and backward syllogism (question derivation).

## [2] First-Order Inference
Extending the logic by introducing compound terms and derived copulas, using ideas in set theory, while still keeping the term vs. statement distinction.

### NAL-2
NAL-2 adds _similarity, instance_, and _property_ copulas that are all defined using _inheritance_ copula. Also introduced are sets with a singular instance or property.

### NAL-3
NAL-3 introduces compound terms in its general form, using set-theoretic connectors _intersection_ and _difference_.

### NAL-4
NAL-4 maps arbitrary (non-copula) relations into _inheritance_, with the help of _product_ and _image_ connector.

## [3] Higher-Order Inference

By dropping the term vs. statement distinction, NAL is extended to include statements-about-statements, and can do inference on them, using ideas from propositional logic and predicate logic.

### NAL-5
NAL-5 introduce _implication_ and _equivalence_ as isomorphic to _inheritance_ and _similarity_, respectively. It also contains additional rules that are specific to statement-level inference, such as _negation_.

### NAL-6
NAL-6 introduces _variable terms_ into NAL. Consequently, the extensional statements and intensional statements can be expressed and processed separately. The logic can also carry out hypothetical and abstract inference.

## [4] Procedural Inference
### NAL-7
NAL 7 introduces time into the system and elevate system's reasoning to another level. Systems gains abilities to predict future events based on its experience. The concepts of temporal inference are a little more substantial to put them here in NAL overview and therefore a dedicated page of [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference) has been created.
### NAL-8
In NAL-8 procedural interpretation is applied to events so declarative and procedural knowledge are unified it also introduces goals and planning. Similar to NAL-7 It is described on separate page in detailed, please look for [Procedural Inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) and [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) pages
### NAL-9
In NAL-9 introspective inference will be mainly implemented as a set of mental operations whose major consequences are within the system itself. These operations carries out various types of self-monitoring and self-control. Please look  [introspective inference](https://github.com/opennars/opennars/wiki/Introspective-Inference) page for more details.





