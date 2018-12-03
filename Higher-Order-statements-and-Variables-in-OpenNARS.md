The content described on this page is often refereed in literature as [NAL-5 and NAL-6](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS)

#### Statements
Concept of a statement as a term and "fills" the gap between the first and higher order interference. Please notice the difference between "statement" and "term as a statement", the former has meaning and **truth value** while the later has only meaning. For example consider statement: <(*,{Peter}, <sky --> [blue]>) ==> say>. %_f, c_%, here the entire statement has truth value and term <sky --> [blue]> within product operator is a statement it self with just a meaning.

NAL 5 defines two new copulas, **implication** (==>) and **equivalence** (<=>), intuitively they correspond to "if then" and "if and only if" meanings and are defined only between statements. _Implication_ and _equivalence_ are defined similarly to _inheritance_ and _similarity_ and therefore one can establish correspondence between of first and higher order NALs. See the table below:

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

### Variable Terms
Terms in earlier layers are **constants terms** that is they are unique in entire system's beliefs, while a **variable term** is unique within a single judgement.  The meaning of a constant terms is determined by its experienced relations with other terms within the system while meaning of a variable term is determined locally  by its relation within the same judgement. i.e. if there are more than one variable name in different judgement they are totally unrelated. Variable terms are always preceded with question or hash marks, "?" or "#" 

Consider the basic inheritance example from NAL-1, S → P, using higher-order NALs it can be rewritten as _((?x → S) ⇒
(?x → P)) ∧ ((P → ?y) ⇒ (S → ?y))_ where _x_ and _y_ are variable terms. Meaning of inheritance can also be described through intension/extension of a term, that is "**if** something (x) is in extension of S that something is in extension of P, and **if** there is other thing (y) in intension of P it is in intension of S". Variables become necessary when extension/intension of term need to be specified separately and intuitively correspond to meaning of "it" pronoun in natural language.  

There are three types of variables used in the system: _independent_, _dependent_ and _query_, [this page](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS) describes the usage of all three types.

**Independent variable** (preceded by "?") **always appears at both sides** of an implication or equivalence relation. It can be substituted by another term without changing the truth value of a judgment, and then a conclusion can be derived.  Substitution of an independent variable is a _unification_ process.

**Dependent variable** (preceded by "#") refer to a specific term. Intuitively, they allow talking about a thing without having to name it. Dependent variable is only introduced into a **conjunction**

**Query variable** is a variable term in a question, not a judgement, that represents a term to be found to answer the question

Given that inheritance can be represented using implication and use of variables specifying intension/extension of a term, truth functions remain the same where inheritance in premises is being rewritten with use of variables.
