OpenNARS operates on logic layers called NALs, there are nine NAL levels (NALs 1-9). NAL levels are added one by one each of which expands the features and capabilities of a previous layer including the [grammar](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS), [inference rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules) and [truth functions](https://github.com/opennars/opennars/wiki/Truth-Functions). Each NAL layer is accompanied with a corresponding Narsese  grammar resulting in 9 Narsese grammars. This article presents each level and briefly describes its features, grammar definition will be omitted from this page instead detailed use of Narsese grammar for each NAL level is outlined [here](https://github.com/opennars/opennars/wiki/Narsese-Grammar,-Language-of-OpenNARS).
In general nine NAL levels are divided into two groups: **First-Order Inference (NALs 1-4)** and **Higher-Order Inferences (NALs 5-8)**

## First-Order Inference (NALs 1-4)
### NAL-1
NAL-1 is a logical foundation of OpenNARS, it is described [here](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS). it operates on well known [syllogistic inference rules](https://github.com/opennars/opennars/wiki/Basic-Syllogistic-Rules), introduces **[Inference rules](https://github.com/opennars/opennars/wiki/Revision-and-Choice-Rules)** and **[Truth Functions](https://github.com/opennars/opennars/wiki/Truth-Functions)**.
### NAL-2
NAL-2 adds similarity, instance and property relations and slightly modifies truth functions. Details are outlined on["Basic Inference" page](https://github.com/opennars/opennars/wiki/Basic-Inference-in-OpenNARS) 
### NAL-3
NAL-3 introduces compound terms and adds operation on the sets such as set intersection and set difference. Details can be found [here](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS)
### NAL-4
NAL-4 allows for "ordinary relations", that are the relations not present in previous NAL layers. Please look for [set operations](https://github.com/opennars/opennars/wiki/Sets-and-set-operations-in-OpenNARS) in OpenNARS

## Higher-Order Inference (NALs 5-8)
As one may notice, in the "first-order" inference, statements are relations among terms, but a statement **cannot** be treated as a term. In "Higher-Order" inference, a statement can be treated as a term, as a statement itself and finally become statement on statements (higher order statements). Thus, grammar, truth functions and syllogistic inference rules are extended to higher NALs preserving most of the previously introduced concepts.
### NAL-5
NAL-5 is the lowest level of higher-order inference, it mainly introduces concept of a statement as a term and "fills" the gap between the first and higher order interference. Please navigate to ["Statements and Variables"](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS) to find more information on statements. 
### NAL-6
NAL 6 introduces **variable terms** into the system. The details can be found on ["Statements and Variables"](https://github.com/opennars/opennars/wiki/Statements-and-Variables-in-OpenNARS) page, while detailed examples of variables are [here](https://github.com/opennars/opennars/wiki/Use-of-Variables-in-OpenNARS).
### NAL-7
NAL 7 introduces time into the system and elevate system's reasoning to another level. Systems gains abilities to predict future events based on its experience. The concepts of temporal inference are a little more substantial to put them here in NAL overview and therefore a dedicated page of [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference) has been created.
### NAL-8
In NAL-8 procedural interpretation is applied to events so declarative and procedural knowledge are unified it also introduces goals and planning. Similar to NAL-7 It is described on separate page in detailed, please look for [Procedural Inference](https://github.com/opennars/opennars/wiki/Procedural-Inference) and [backward inference](https://github.com/opennars/opennars/wiki/Backward-Inference-in-OpenNARS) pages
 





