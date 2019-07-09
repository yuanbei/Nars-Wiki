The content described on this page is part of [NAL-5](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-the-logic-behind-OpenNARS)

### Statement as term

Since in Narsese a statement can be used as a term in a compound term (including a statement), and a term can be used as (the name of) a statement, the difference between "term" and "statement" becomes that a statement can be given a truth-value, while a (non-statement) term cannot (e.g., _bird_ has no truth-value).

When a statement has another statement as a component, it is referred to as a "higher-order statement", and the inference on it "higher-order inference". The embedded statement in another statement can be higher-order itself, and there is no limit on the level of embedding, though complicated statements formed in this way will get less and less attention, and is easily forgotten soon. In a higher-order statement, only the outer-most statement gets a NAL truth-value, while all the component-statements in it get binary truth-values (true/false).

For example consider statement: _<(*, {Peter}, {<sky --> [blue]>}) --> say>. %f;c%_ ("Peter says that the sky is blue"), here the entire statement has a NAL truth value, while the term  _<sky --> [blue]> _ is a statement itself, with a binary truth-value (as being "true").

### Stement-level copulas

NAL-5 introduces two copulas that are defined only between statement, **implication** (==>) and **equivalence** (<=>), intuitively corresponding to "if then" and "if and only if", respectively. _Implication_ and _equivalence_ are defined similarly to _inheritance_ and _similarity_ and therefore one can establish correspondence between of first and higher order inference. See the table below:

**First-Order <--------------------------> Higher-Order** <br/>
_term <---------------------------------> statement_<br/>
_inheritance <--------------------------> implication_<br/>
_similarity <---------------------------> equivalence_<br/>
_subject <------------------------------> antecedent_<br/>
_predicate <----------------------------> consequent_<br/>
_extension <----------------------------> sufficient condition_<br/>
_intension <----------------------------> necessary condition_<br/>
_extensional intersection <-------------> conjunction_<br/> 
_intensional intersection <-------------> disjunction_<br/>

Given the correspondence, most first-order inference rules can be mapped isomorphically to higher-order. Some term connectors (such as sets, product, and images) treat statements as ordinary terms, so the related inference rules are used in both first-order and higher-order inference without any change.

### Negation

In first-order NAL, there is no "term negation" (so "non-bird" is not a valid concept), but only "term difference" (so "animals other than birds" is a valid concept). In higher-order NAL, statement-level negation is introduced. For a statement with a NAL truth-value, the truth-value of its negation is obtained by switching its positive and negative evidence, so for the statement _S. %f;c%_, its negation is (--, S). _%1-f; c%_.

For an embedded statement, its negation is the same as binary (Boolean) negation.

In NAL, the traditional _Law of Contrapositive_  (S ==> T ≡ ¬T ==> ¬S) is no longer true, since the two statements only share negative evidence, but have distinct positive evidence.

