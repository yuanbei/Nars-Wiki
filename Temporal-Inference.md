Temporal Inference is introduced in OpenNARS with [NAL 7](https://github.com/opennars/opennars/wiki/Non-Axiomatic-Logic-(NAL),-Logic-behind-OpenNARS) that introduces time into the statement.

## Event and Time

All statements in OpenNARS are time dependent including the ones that are defined in "first order" inference. This happens because in most cases truth value of a statement is being changed during inference steps for some period of time and only rarely empirical statement holds its truth value for some time interval. However for efficiency and implementation purposes, it is not possible and not always necessary taking the "time" attribution of a statement into consideration. Therefore events, as some type of a statement, are introduced into the system starting with NAL 7.

**An event** is a statement with a _time-dependent truthvalue_, that is, the evidential support summarized in its truth-value is valid only in its duration, which is a certain period of time between the moment the event starts and the moment it ends.



