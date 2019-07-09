### Variable Terms

Ordinary terms NAL are **constants terms** in the sense that each of them names the same concept, and if the same term appears in multiple sentences, they are all about the same thing, so their meaning is _global_ (defined in the whole memory). On the contrary, a ***variable term*** may be used in different sentences to indicate different concepts, so their meaning is _local_ (defined in a sentence).

[Narsese grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar-(Input-Output-Format)) includes three types of variable terms:
* An **independent variable** (with the prefix "$") represents an **arbitrary** term in the extension or intension of another term and normally appears at both sides of an _implication_ or _equivalence_ copula showing the relationship between the extensions (or intensions) of two terms. It loosely corresponds to variables under the universal ("for all") quantifier in first-order predicate logic.
* A **dependent variable** (with the prefix "#") represents an **anonymous** term in the extension or intension of another term and normally appears at multiple components of a _conjunction_ showing the relationship between the extensions (or intentions) of the terms. It loosely corresponds to variables under the existential ("there is") quantifier in first-order predicate logic.
* A **query variable** (with the prefix "?") is a variable term in a question or goal that represents a term to be found or created. It loosely corresponds to variables in goals of logic programming languages (such as Prolog).

The following table lists some typical statements with variable terms: 
```
              independent                   dependent                    query
extensional   <<$x --> S> ==> <$x --> P>>   (&&,<#x --> S>,<#x --> P>)   <?x --> P>
intensional   <<P --> $x> ==> <S --> $x>>   (&&,<S --> #x>,<P --> #x>)   <S --> ?x>
```

### Inference with valuable terms

Inference on statements with variable terms usually requires one extra step just for the variable(s) before or after an inference rule is used as usual:
* **Variable introduction:** To replace a constant by a variable. E.g., turning an inductive conclusion from _<<A --> B> ==> <A --> C>>_ to _<<$x --> B> ==> <$x --> C>>_ as a generalization.
* **Variable elimination:** To replace a variable by a constant. E.g., turning a premise from _<<$x --> B> ==> <$x --> C>>_ to _<<A --> B> ==> <A --> C>>_, so it can do deduction with another premise _<A --> B>_ to get _<A --> C>_. For a query variable, it is used to find a solution _<S --> P>_ for the question _<?x --> P>_.
* **Variable unification:** To replace a variable by another variable. E.g., from _<<$x --> A> ==> <$x --> B>>_ and _<<$y --> B> ==> <$y --> C>>_ to derive _<<$z --> A> ==> <$z --> C>>_ by deduction.

The truth-value function used in the step depends on the nature of the inference.

### Usages of variable terms

One reason to use a variable term is to separate the extensional factor and intensional factor of an _inheritance_ statement. For example, _<S --> P>_ is often a efficient summary of _<<$x --> S> ==> <$x --> P>>_ and _<<P --> $x> ==> <S --> $x>>_, but there are situations where the latter two have very different truth-values, so need to be separate from other other. The other copulas have similar needs.

Note the difference between questions "Are there red apples?" and "Which is a red apple?", which are expressed respectively as
```
(&&,<#1 --> [red]>,<#1 --> apple>)?
(&&,<?1 --> [red]>,<?1 --> apple>)?
```
or equivalently as
```
<#1 --> (&,[red],apple)>?
<?1 --> (&,[red],apple)>?
```
In either form, they are different questions, where the former only asks for a truth-value, while the latter asks for a concrete instance. 

### Examples

Different types of variables can be used together in several ways to represent something more complicated. For example, the "uncle" relation in Prolog can be defined as:
``` 
uncle(X,Z) :- brother(X,Y), parent(Y,Z).
```
In Narsese, a similar representation is:
```
<(&&,<(*,$1,#2) --> brother>,<(*,#2,$3) --> parent>) ==> <(*,$1,$3) --> uncle>>.
```
Therefore, if the following is entered into OpenNARS

```
<(*,{john},{tom}) --> parent>.
<(*,{tim},{john}) --> brother>.
<(*,{?who},{?ofWho}) --> uncle>?
```
you will get
```
Answer <(*,{tim},{tom}) --> uncle>. %1.00;0.73%
```
More complicated cases are given in the example files of NAL-6, like "Every lock can be opened by some key" is expressed as:
```
<<$x --> lock> ==> (&&,<#y --> key>,<$x --> (/,open,#y,_)>)>. 
```