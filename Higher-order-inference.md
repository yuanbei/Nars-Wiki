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

Because of such correspondence, the following inference rules are defined similarly in NAL 5: choice, revision, conversion, comparison, analogy, induction, deduction, abduction and exemplification. Term operators introduced in earlier layers such as sets, product, image and ordinary relation treat "higher order" statements just like "first order" terms.

NAL-5 also introduces **Negation**, that is a negation of a statement is a compound term with positive and negative evidence switched. For the statement \<S> _%f0; c0%_, its negation is <(--, S)> _%f1; c1%_ where negation truth function is then defined as:<br/>

**F negation truth value:** _f = 1 - f0, c = c0_

Important to note that _Law of Contrapositive_  (S => T ≡ ¬T => ¬S) is no longer true, therefore NAL-5 introduces another variant of conversion rule from NAL-1 that is from  <S1 ==> S2>  %f0; c0%  NAL derives <(--, S2) ==> (--, S1)> %f1; c1% where truth value is computed using <br/>
**F conversion3:** _f=0, c = (1-f0)c0/(f0c0 + 1)_
