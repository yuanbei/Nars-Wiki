OpenNARS operates on logic layers called NALs, there are nine NAL levels (NALs 1-9). NAL levels are added one by one each of which expands the features and capabilities of a previous layer including the [grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), inference rules and [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions). This article introduces each level and briefly describes its features.

In general nine NAL levels are divided into two groups: **First-Order Inference (NALs 1-4)** and **Higher-Order Inferences (NALs 5-9)**

## First-Order Inference (NALs 1-4)
### NAL-1

NAL-1 is a logical foundation of OpenNARS it it features well known LOGICAL inference rules of _[deduction](https://en.wikipedia.org/wiki/Deductive_reasoning), [abduction](https://en.wikipedia.org/wiki/Abductive_reasoning), [induction](https://en.wikipedia.org/wiki/Inductive_reasoning) and exemplification_. 
{M → P <f1, c1 >, S → M <f2, c2 >} |-- S → P <f, c>
This is Aristotle’s first figure, and what Peirce called deduction.




