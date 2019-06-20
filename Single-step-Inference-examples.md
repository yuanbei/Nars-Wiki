There are example files distributed with the executable version of OpenNARS, in the directory  _bin_lab/nal/single_step/_, where each _*.nal_ file contains the sample input and output of an inference rule in plain ASCII code.

An example looks like the following:
```
'Revision ------

'Bird is a type of swimmer.
<bird --> swimmer>.

'Bird is probably not a type of swimmer.
<bird --> swimmer>. %0.10;0.60%

1

'Bird is very likely to be a type of swimmer.
''outputMustContain('<bird --> swimmer>. %0.87;0.91%')
```

********** revision
  IN: <bird --> swimmer>.
  IN: <bird --> swimmer>. %0.1;0.6%
1
 OUT: <bird --> swimmer>. %0.87;0.91% {2: 2;1} 
A line starting with '*' indicates the beginning of a new example, and will initialize the system when feed into the demo as input. A line starting with '/' is a comment. A line starting with an optional "IN:" is an input task to the system, and a line starting with "OUT:" is output from the system. A line containing a single number indicates the number of inference cycles between in/out lines. Spaces, tabs, and blank lines are ignored.

String like "<bird --> swimmer>. %0.87;0.91%" is a Narsese sentence, and the grammar is specified in InputOutputFormat. The following "{2: 2;1}" is a 'stamp' automatically attached by the system, to indicate the source of that line.

The demonstration of NARS, under nars-dist, can run the examples in two ways: when the system runs as either application or applet, the user can use copy/paste an example into the input window, then click "OK" to run the example as instructions. In this process, the output lines and the stamps will be ignored. When the system runs as an application, the user can also load a complete example file, by choosing it from the Main Window, using "File/Load experience". Since the input/output line produced in this way will be quickly overwritten in the display area, it is necessary to save it into a file, using "File/Save experience". The first time this item is selected, the user can open a (new or existing) file to catch the user/system communication. To close the file, select "File/Save experience" again.

With this file load/save function, each example file comes with two versions. The "abridged" version is manually edited to only contain the relevant information for each example, so is easier to understand; the "complete" version contains all actual user/system communication as displayed then the "abridged" version is feeded into the system. It means, if a "complete" version is loaded into the system as input, the output (saved into another file) should be an identical copy. This will be useful in testing, when the changes made in the system should not cause any difference in the system's input/output mapping.

The examples are grouped according to the order they are introduced in the book Rigid Flexibility: The Logic of Intelligence. They are not self-explained, and the readers should consult the book to fully understand them.

Single step Inference examples

* [NAL-1: Basic Syntax, Semantics and Inference Rules](https://github.com/opennars/opennars/wiki/NAL-1:-Basic-Syntax,-Semantics-and-Inference-Rules)
* [NAL-2: Derivative Copulas](https://github.com/opennars/opennars/wiki/NAL-2:-Derivative-Copulas)
* [NAL-3: Set-Theoretic Terms](https://github.com/opennars/opennars/wiki/NAL-3:-Set-Theoretic-Terms)
* [NAL-4: Relational Terms](https://github.com/opennars/opennars/wiki/NAL-4:-Relational-Terms)
* [NAL-5: Statements as Terms](https://github.com/opennars/opennars/wiki/NAL-5:-Statements-as-Terms)
* [NAL-6: Variable Terms](https://github.com/opennars/opennars/wiki/NAL-6:-Variable-Terms)
* [NAL-7: Events as Statements](https://github.com/opennars/opennars/wiki/NAL-7:-Events-as-Statements)
* [NAL-8: Operations and Goals as Events](https://github.com/opennars/opennars/wiki/NAL-8:-Operations-and-Goals-as-Events)
* [NAL-9: Self-Monitoring and Self-Control](https://github.com/opennars/opennars/wiki/NAL-9:-Self-Monitoring-and-Self-Control)