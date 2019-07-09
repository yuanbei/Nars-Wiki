### Variable Terms

Ordinary terms NAL are **constants terms** in the sense that each of them names the same concept, and if the same term appears in multiple sentences, they are all about the same thing, so their meaning is _global_ (defined in the whole memory). On the contrary, a ***variable term*** may be used in different sentences to indicate different concepts, so their meaning is _local_ (defined in a sentence).

[Narsese grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)) includes three types of variable terms:
* **Independent variable** (with prefix "$") represents an **arbitrary** term in the extension or intension of another term, and normally appears at both sides of an _implication_ or _equivalence_ copula showing the relationship between the extensions (or intensions) of two terms.
* **Dependent variable** (with prefix "#") represents an **anonymous** term in the extension or intension of another term, and normally appears at multiple components of a _conjunction_ or disjunction showing the relationship between the extensions (or intensions) of the terms.
* **Query variable** is a variable term in a question or goal, that represents a term to be found or created




Consider the basic inheritance example from NAL-1, S → P, using higher-order NALs it can be rewritten as _((?x → S) ⇒
(?x → P)) ∧ ((P → ?y) ⇒ (S → ?y))_ where _x_ and _y_ are variable terms. Meaning of inheritance can also be described through intension/extension of a term, that is "**if** something (x) is in extension of S that something is in extension of P, and **if** there is other thing (y) in intension of P it is in intension of S". Variables become necessary when extension/intension of term need to be specified separately and intuitively correspond to meaning of "it" pronoun in natural language.  



Given that inheritance can be represented using implication and use of variables specifying intension/extension of a term, truth functions remain the same where inheritance in premises is being rewritten with use of variables.

 It can be substituted by another term without changing the truth value of judgment.  

> ### Variable Usage
> When to use what variable type
***


### Introduction
The variable terms has been introduced in NAL 6 and they often create confusion. This page provides an explanation about various ways to use different variable types.

***
### Independent Variables
They represent any unspecified term that matches the pattern the variable occurs in, and has to start with "$". Intuitively they allow saying things like: "Whenever something has a this property (or instance), it also has that property (or instance)".

This type of variable typically appears as the common subject term or predicate term of two inheritance statements in an implication or equivalency statement. They correspond at least loosely to variables under the universal ("for all") quantifier in first order logic.

Example:

Something which is a cat, is also an animal

`<<$1 --> cat> ==> <$1 --> animal>>.`
(Independent vars must appear on both sides of the implication)

***
### Dependent Variables

They refer to a specific term and have to start with "#". Intuitively, they allow talking about a thing without having to name it.

This type of variable typically appears as the common subject term or predicate term of two (or more) inheritance statements in a conjunction. They correspond at least loosely to variables under the existential ("there is") quantifier in first order logic.

Example: There are red apples.

`(&&,<#1 --> [red]>,<#1 --> apple>).`
***
### Query Variables

Used just as placeholder for a specific constant statement to ask about:

Who is a cat?

`<?1 --> cat>?`

Note the difference to for example "Are there red apples?" and "Which is a red apple?" are expressed respectively as

`(&&,<#1 --> [red]>,<#1 --> apple>)?`

`(&&,<?1 --> [red]>,<?1 --> apple>)?`

where the former only asks for a truth-value, while the latter asks for a concrete instance.

***
### Mixed Examples

Different types of variable can be used together in several ways to represent something more complicated. For example, the "uncle" relation in Prolog can be defined as: uncle(X,Y) :- parent(Z,Y), brother(X,Z).

In Narsese, a similar representation is:

```
<(&&,<(*,$1,#2) --> brother>,<(*,#2,$3) --> parent>) ==> <(*,$1,$3) --> uncle>>. %1.00;0.90%
```

Let's try with:

```
<(*,{john},{tom}) --> parent>.
<(*,{tim},{john}) --> brother>.
<(*,{?who},{?ofWho}) --> uncle>?
```

works:

`Answer <(*,{tim},{tom}) --> uncle>. %1.00;0.73%`

More complicated cases: "Every lock can be opened by some key" is expressed as:

`<<$x --> lock> ==> (&&,<#y --> key>,<$x --> (/,open,#y,_)>)>. `

Interesting NAL9 case which involves all variable types:

"Who is similar to Tom?" is a good question.

`<{<?who <-> Tom>} --> (&, [good], question)>.`

If something is a good question, and someone asks himself the question then he is a good agent.

```
<(&&,<#1 --> (&, [good], question)>, <(*, {$2}, #1) --> wonder>) ==> <({$2} --> (&, [good], agent)>>.
```

NARS is a agent

`<{NARS} --> agent>.`

NARS should also be good

`<{NARS} --> [good]>!`

As a result, in order to make the goal true, it will ask who is similar to Tom.
***
### Syllogistic Pattern

Dependent Variables and Independent Variables only get introduced in the following semantic patterns:

```
               independent                    dependent
extensional    <<$x --> S> ==> <$x --> P>>    (&&,<#x --> S>,<#x --> P>)
intensional    <<P --> $x> ==> <S --> $x>>    (&&,<S --> #x>,<P --> #x>) 
```

and for equivalence

```
               independent                    dependent
extensional    <<$x --> S> <=> <$x --> P>>    <#x --> (&,S,P)>
intensional    <<P --> $x> <=> <S --> $x>>    <(|,P,S) --> #x>
```

For example <<$x --> S> ==> <$x --> P>>. can be created based on <a --> S> and <a --> P> because <<$x --> S> ==> <$x --> P>> matches <<$x --> S> ==> <$x --> P>> by instantiating $x with a.