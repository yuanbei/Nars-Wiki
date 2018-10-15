A typical simple inference cycle in OpenNARS takes two judgements as premise and derives a judgement as a conclusion. An example looks like:<br/>
**_{\<premise1\>. %f1, c1%, \<premise2\>. %f2, c2%} |-- conclusion %f,c%_**

Given a certain syllogistic rule applied to derive a conclusion, the truth value of a conclusion is being computed using **truth function**.  

There are four truth functions (F) that are applied in correspondence with syllogistic rule:
1. _F deduction_
2. _F abduction_
3. _F induction_
4. _F exemplification_

Truth functions presented here outline basic ideas and correspond to the first logical level NAL-1, a logical foundation of OpenNARS. NAL levels are added one by one each of which expands the grammar, inference rules and slightly modifies truth function to accommodate a higher capability of a corresponding NAL. Although truth functions undergo a slight modification in a higher NAL levels their meaning and application remains the same. 
 