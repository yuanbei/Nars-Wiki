Information present on this page is closely related to the following pages: [sentence](https://github.com/opennars/opennars/wiki/Sentence:-types,-format), [task](https://github.com/opennars/opennars/wiki/Tasks-Management-in-OpenNARS),[truth value](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples), [budget value](https://github.com/opennars/opennars/wiki/Budget-Value), [evidential basis](https://github.com/opennars/opennars/wiki/Data-structure-for-evidential-basis,-beliefs-and-goals), ["bag"](https://github.com/opennars/opennars/wiki/System-Memory-(bag,-overall-structure)), [control mechanism](https://github.com/opennars/opennars/wiki/Working-Cycle), [concepts](https://github.com/opennars/opennars/wiki/Concept-Object:-Content-and-Attributes) and [type of links](https://github.com/opennars/opennars/wiki/Types-of-Links:-task-and-term-links) in OpenNARS. Please feel free to read them before in process of reading this page.

From a user perspective, a sentence is just a Narsese string with attached truth value, basically a string of ASCII characters. For example, <raven --> [black]>. is a sentence (string of characters) one would enter into input section of GUI of OpenNARS. It is not necessary even to enter a truth value during input since the system will assign a default truth value. However in the system and implementation sense, sentence has much broader meaning then just a string of ASCII characters.  

In OpenNARS **sentence** is a container, it is an object that contains multiple elements: compound term, punctuation, truth value and stamp. Sentence itself resides inside a Task object which has budget value and stored in task buffer. Content of the sentence is discussed below in detail.

### Compound term
Statement of a sentence (basically sentence without a truth value) in a system is represented as a [compound term](https://github.com/opennars/opennars/wiki/Term:-types,-format) with copula relation. For example, <raven --> [black]> is treated as a compound term with two terms, and copula as an operation. Statement is being parsed recursively until atomic term as a word is reached and operator as a copula is being applied. During recursive descend concepts for terms are being created and all dependent links are initialized or updated. For above example, atomic terms are "raven" and "black" and operation is an "inheritance" copula.

### Stamp
Stamp is an object itself. It has evidential basis, that is a derivation history of the sentence, occurrence time and creation time. Creation time is a long integer value which indicates when a sentence was created in terms of milliseconds or working cycles of the system, it does not participate in any inference, but used for information only that is useful for debugging and trace of derivation process. Occurrence time is also a long value which indicates at what millisecond or what working cycle the sentence and its corresponding task has to occur. It is used for [temporal inference](https://github.com/opennars/opennars/wiki/Temporal-Inference) to indicate an event is occurred before, after or at the same time relative to some other event. Occurrence time is independent of creation time, that is it can be less, equal or greater than creation time meaning as an information about past, present or future. For input temporal tasks occurrence time is equal to creation time. For non-temporal tasks, occurrence time is initialized with a default value.     

### Punctuation
Punctuation is just a character value of ".", "!", "?" or "@" to indicate if sentence is a judgment, goal, question or quest.

### Truth value
Generic OpenNARS truth value with frequency and confidence

Diagram below shows sentence within the input task for better understanding.

