OpenNARS is the open-source implementation of NARS (Non-Axiomatic Reasoning System), while NARS is based on NAL (Non-Axiomatic Logic).

Conceptually, NAL is defined hierarchically with multiple layers, each of them extends the logic by introducing new grammar rules and inference rules, so as to make the logic more and more powerful in its expressing and inferencing capability. For educational purpose, it is suggested to learn the system in this order. However, the separation of the layers are ignored in implementation, so in the code, the rules in each layer cannot be clearly distinguished from each other. 

The complete NAL grammar is specified in the [grammar page](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), while the inference rules are described in multiple pages, with their truth functions summarized in the [truth-value function page](https://github.com/opennars/opennars/wiki/Truth-Functions). 

In the current design, NAL consists of 9 layers in 4 groups, in the sense that it is possible to only implement one group plus the layer below it to get a functional system with well-defined capability.

## [1] Basic Inference
The simplest non-axiomatic logic, with atomic terms and single copula.
### NAL-1
NAL-1 is a logical core of NAL. The statements in it are all inheritance statements with an atomic subject and an atomic predicate. The meaning of a term is defined as its extension and intention. The truth value of a statement measures its evidential support. The inference rules include local rules (revision and choice), forward syllogism (deduction, induction, abduction), and backward syllogism (question derivation).

## [2] First-Order Inference
Extending the logic by introducing compound terms and derived copulas, using ideas in set theory.

### NAL-2
NAL-2 adds similarity, instance, and property copulas that are all based on inheritance copula. Also introduced are sets with a singular instance or property.

### NAL-3
NAL-3 introduces compound terms in its general form, using set-theoretic connectors _intersection_ and _difference_.

### NAL-4
NAL-4 allows for "ordinary relations", that are the relations not present in previous NAL layers. Please look for [set operations](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS) in OpenNARS

## [3] Higher-Order Inference
As one may notice, in the "first-order" inference, statements are relations among terms, but a statement **cannot** be treated as a term. In "Higher-Order" inference, a statement can be treated as a term, as a statement itself and finally become statement on statements (higher order statements). Thus, grammar, truth functions and syllogistic inference rules are extended to higher NALs preserving most of the previously introduced concepts.
### NAL-5
NAL-5 is the lowest level of higher-order inference, it mainly introduces concept of a statement as a term and "fills" the gap between the first and higher order interference. Please navigate to ["Statements and Variables"](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS) to find more information on statements. 
### NAL-6
NAL 6 introduces **variable terms** into the system. The details can be found on ["Statements and Variables"](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS) page, while detailed examples of variables are [here](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS).

## [4] Procedural Inference
### NAL-7
NAL 7 introduces time into the system and elevate system's reasoning to another level. Systems gains abilities to predict future events based on its experience. The concepts of temporal inference are a little more substantial to put them here in NAL overview and therefore a dedicated page of [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference) has been created.
### NAL-8
In NAL-8 procedural interpretation is applied to events so declarative and procedural knowledge are unified it also introduces goals and planning. Similar to NAL-7 It is described on separate page in detailed, please look for [Procedural Inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) and [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) pages
### NAL-9
In NAL-9 introspective inference will be mainly implemented as a set of mental operations whose major consequences are within the system itself. These operations carries out various types of self-monitoring and self-control. Please look  [introspective inference](https://github.com/opennars/opennars/wiki/Introspective-Inference) page for more details.





