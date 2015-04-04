# VariableUsage
When to use what variable type

***
### Introduction
The variable terms of NAL sometimes create confusion. This article is an explanation about when to use which variable type, also some intuitive examples are given.

***
### Independent Variables
They represent any unspecified term that matches the pattern the variable occurs in, and has to start with "$". Intuitively they allow saying things like: "Whenever something has a this property (or instance), it also has that property (or instance)".

This type of variable typically appears as the common subject term or predicate term of two inheritance statements in an implication or equivalency statement. They correspond at least loosely to variables under the universal ("for all") quantifier in first order logic.

Example:

Something which is a cat, is also an animal

`<<$1 --> cat> ==> <$1 --> animal>>.`
***
### Dependent Variables

They refer to a specific term and have to start with "#". Intuitively, they allow talking about a thing without having to name it.

This type of variable typically appears as the common subject term or predicate term of two (or more) inheritance statements in a conjunction. They correspond at least loosely to variables under the existential ("there is") quantifier in first order logic.

Example: There are red apples.