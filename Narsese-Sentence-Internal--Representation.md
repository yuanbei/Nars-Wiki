Information present on this page is closely related to the following pages: [sentence](https://github.com/opennars/opennars/wiki/Sentence:-types,-format), [truth value](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples), [budget value](https://github.com/opennars/opennars/wiki/Budget-Value), ["bag"](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)), [control mechanism](https://github.com/opennars/opennars/wiki/Working-Cycle), [concepts](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) and [type of links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links) in OpenNARS.




Please feel free to read them before in process of reading this page.

From a user perspective, a sentence is just a Narsese string with attached truth value, basically a string of ASCII characters. For example, <raven --> [black]>. is a sentence (string of characters) one would enter into input section of GUI of OpenNARS. It is not necessary even to enter a truth value during input since the system will assign a default truth value. However in the system and implementation sense, sentence has much broader meaning then just a string of ASCII characters.  

In OpenNARS sentence is a container, it is an object that contains multiple elements: compound term, punctuation, truth value, budget value and stamp.  They are discussed below in detail.


