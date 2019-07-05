A typical simple inference rule of NAL takes two premises and derives a conclusion, in the following pattern:<br/>
**_{\<premise1\>. %f1; c1%, \<premise2\>. %f2; c2%} |- \<conclusion\>. %f; c%_**

The truth-value function of the rule calculates _%f; c%_ from _%f1; c1%_ and _%f2; c2%_. According to the definition of truth-value in NAL, the result of the function should correctly indicate the evidential support the conclusion obtained from the premises (alone).

The function is defined in the following procedure:
1. Treat all the variable as binary (Boolean), and analyze how the variables are related to each other, according to the semantics.
2. Find simple and natural Boolean functions to relate these variables.
3. Replace the Boolean operators by their [extended forms](https://github.com/opennars/opennars/wiki/Extended-Boolean-Functions-in-OpenNARS)
4. Rewrite the relations as a function that maps _%f1; c1%_ and _%f2; c2%_ to _%f; c%_.

All the truth-value functions are explained in detail in  [Non-Axiomatic Logic](https://www.worldscientific.com/worldscibooks/10.1142/8665), and listed in its [Appendix C](https://doi.org/10.1142/9789814440288_bmatter). There is also [an Excel table](http://www.cis.temple.edu/~pwang/Implementation/NAL/NAL-TruthFunctions.xls) that allows simple experiments with the functions.

As far as the [Basic Syllogistic Rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules) are concerned,

Given a certain syllogistic rule applied to derive a conclusion, the truth value of a conclusion is being computed using **truth function**.  

There are four truth functions (F) that are applied in correspondence with syllogistic rule:
1. _F deduction_
2. _F abduction_
3. _F induction_
4. _F exemplification_

Truth functions presented here outline basic ideas and correspond to the first logical level NAL-1, a logical foundation of OpenNARS. NAL levels are added one by one each of which expands the grammar, inference rules and slightly modifies truth functions to accommodate a higher capability of a corresponding NAL. Although truth functions undergo a slight modification in a higher NAL levels their meaning and application remains the same. 

### _F deduction_

Suppose two premises are  \<S --> M\>.%f1; c1% and \<M --> P\>. %f2; c2%, then using **deduction** syllogistic rule OpenNARS will derive conclusion  \<S -- > P\> %f; c%. 
Truth value of the conclusion is then a simple multiplication of truth values of premises:<br/>

**_F deduction_: f = (f1 * f2) and c = (f1 * c1 * f2 * f2)**
<br/><br/>
A chain of deduction can be formed by more than two judgments, and F deduction can be applied multiple times. For example given premises: _\<a -->b\>. %f1; c1%,  \<b --> c\>. %f2; c2% and  \<c --> d\>. %f3; c3%_, a judgment on _\<a-->d\> %f; c%_ can be formed by applying the deduction rule and _F deduction_ twice.

### _F abduction_

Suppose two premises are  _\<P --> M\>. %f1; c1%_ and _\<S --> M\>.%f2; c2%_ , then using **abduction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f1 * c1* c2_, Therefore:<br/><br/> 
**_F abduction_: f = f2 and c = (f1 * c1 * f2 * f2)/(f1 * c1 * c2 + k)**
<br/>

### _F induction_

This function is symmetric to the abduction one. Suppose two premises are _\<M --> P\>. %f1; c1%_ and _\<M --> S\>.%f2; c2%_; , then using **induction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f2 * c1* c2_, Therefore:<br/><br/> 
**_F induction_: f = f1 and c = (f1 * c1 * f2 * f2)/(f2 * c1 * c2 + k)**
<br/> 

### _F exemplification_

Exemplification can be considered as "reversed deduction" since it derives an inheritance judgment in the opposite direction of deduction. Negative evidence can not be collected in reverse direction of inheritance and thus not present in exemplification.

Suppose two premises are  _\<P --> M\>.%f1; c1%_ and _\<M --> S\>. %f2; c2%_, then using **exemplification** OpenNARS will derive conclusion _\<S --> P\>. %f; c%_ 
Truth value of the conclusion is defined through the positive and total evidence which are equal since no negative evidence can be collected in reverse direction of inheritance. Thus _positive evidence = f1 * c1 * f2 * c2_ = _total evidence = f1 * c1 * f2 * c2_:<br/><br/> 
**_F exemplification_: f = 1 and c = (f1 * c1 * f2 * f2)/(f1 * f2 * c1 * c2 + k)**
<br/> <br/> 
**Properties:**
* Both frequency and confidence contribute to inference, but in different ways.
* Revision is the only rule where the confidence of the conclusion may be higher than those of the premises.
* The confidence of a syllogistic conclusion is never higher than the confidence of either premise, that is, confidence “declines” in syllogistic inference.
* Confidence declines much slower in deduction than in induction and abduction.
* Positive evidence supports inheritance in both directions, that is order of premises is not important.
* Negative evidence supports inheritance in only one direction, thus order of premises is important.



5. Because of similarity is symmetric, truth functions are modified: 
<br/><br/>
**_F comparison_**<br/>
Suppose two premises are  _\<P --> M\>. %f1; c1%_ and _\<S --> M\>.%f2; c2%_ or _\<M --> P\>. %f1; c1%_ and _\<M --> S\>.%f2; c2%_ then using **comparison** rule OpenNARS will derive conclusion  \<S <--> P\> %f; c%, by comparing the inheritance relations of two terms to a third term. It is easy to see that F comparison is similar to abduction and induction only conclusion is now symmetric.<br/> 
_total evidence w = (f1 + f2 - f1 * f2) * c1 * c2_, and _positive evidence = f1 * c1 * f2 * c2_ Thus, <br/>
**_F comparison_ truth value**: _f = f1*f2/(f1+f2-f1*f2)_ and _c = [c1 * c2 * (f1 + f2 − f1 * f2)]/[c1 * c2 * (f1 + f2 − f1 * f2) + k]_
<br/><br/>
**_F analogy_**<br/> 
Suppose two premises are  _\<S <--> M\>. %f1; c1%_ and _\<M --> P\>.%f2; c2%_ or _\<P --> M\>. %f1; c1%_ and _\<S <--> M\>.%f2; c2%_ then using **analogy** rule OpenNARS will derive conclusion  \<S --> P\> %f; c% or \<P --> S\> %f; c%. The situation is is similar to deduction.Thus, <br/>
**_F analogy_ truth value**: _f = f1*f2_ and _c = c1 * f2 * f2 * c2 * c2_
<br/><br/>
**_F deduction2_**<br/>
Suppose two premises are  _\<S <--> M\>. %f1; c1%_ and _\<M <--> P\>.%f2; c2%_ that is both premises are similarity relations, then using **deduction2** rule OpenNARS will derive conclusion  \<S <--> P\> %f; c%, it can be treated as deduction going in both directions. Thus, <br/>
**_F deduction2_ truth value**: _f = f1*f2_ and _c = c1 * c2 * (f1 + f2 − f1 * f2)_
OpenNARS operates on well known Syllogistic Rules, that provide a foundation to all its logical layers ([NALs](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS)). Below is a brief overview of logical inference rules of _[deduction](https://en.wikipedia.org/wiki/Deductive_reasoning), [abduction](https://en.wikipedia.org/wiki/Abductive_reasoning), [induction](https://en.wikipedia.org/wiki/Inductive_reasoning) and exemplification_. 

 