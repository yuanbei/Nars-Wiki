A typical simple inference cycle in OpenNARS takes two judgements as premise and derives a judgement as a conclusion. An example looks like:<br/>
**_{\<premise1\>. %f1; c1%, \<premise2\>. %f2; c2%} |-- \<conclusion\>. %f; c%_**

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

Suppose two premises are  _\<S --> M\>.%f1; c1%_ and _\<P --> M\>. %f2; c2%_, then using **abduction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f1 * c1* c2_, Therefore:<br/><br/> 
**_F abduction_: f = f2 and c = (f1 * c1 * f2 * f2)/(f1 * c1 * c2 + k)**
<br/>

### _F induction_

This function is symmetric to the abduction one. Suppose two premises are  _\<M --> S\>.%f1; c1%_ and _\<M --> P\>. %f2; c2%_, then using **induction** syllogistic rule OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
Truth value of the conclusion is defined through the positive and total evidence where _positive evidence = f1 * c1 * f2 * c2_ and the _total evidence = f2 * c1* c2_, Therefore:<br/><br/> 
**_F induction_: f = f1 and c = (f1 * c1 * f2 * f2)/(f2 * c1 * c2 + k)**
<br/> 

### _F exemplification_

Exemplification can be considered as "reversed deduction" since it derives an inheritance judgment in the opposite direction of deduction. Negative evidence can not be collected in reverse direction of inheritance and thus not present in exemplification.

Suppose two premises are  _\<P --> M\>.%f1; c1%_ and _\<M --> S\>. %f2; c2%_, then using **exemplification** OpenNARS will derive conclusion _\<S -- > P\> %f; c%_. 
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




 