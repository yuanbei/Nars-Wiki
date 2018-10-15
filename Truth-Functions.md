A typical simple inference cycle in OpenNARS takes two judgements as premise and derives a judgement as a conclusion. An example looks like:<br/>
**_{\<premise1\>. %f1, c1%, \<premise2\>. %f2, c2%} |-- conclusion %f,c%_**

Given a certain logical syllogistic rule applied to derive a conclusion, the truth value of a conclusion is being computed using **truth function**.  

There are four truth functions (F) that are applied in correspondence with syllogistic rule:
1. F deduction
2. F abduction
3. F induction
4. F exemplification

Truth functions presented here outline basic ideas and correspond to the first logical level NAL-1 that provides a logical foundation of OpenNARS. NAL levels are added one by one each of which expands the grammar and inference rules of the logic in a certain way. During description of each logical level, truth function will be slightly modified to accommodate higher capability of a corresponding NAL.
 
 