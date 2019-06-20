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

A line starting with a single quotation mark ' is a comment. A single inference step typically has two premises, each as a sentence in Narsese, and the format is explained in [the grammar page](https://github.com/opennars/opennars/wiki/Input-Output-Format). A line containing a single number indicates the number of inference cycles between lines. Spaces, tabs, and blank lines are ignored.

In the above example, the first premise takes the default [truth-value](https://github.com/opennars/opennars/wiki/Truth-Value:-Definition-and-Examples), while the second takes a specific one. These values can be changed to see the effect on the conclusion.

The examples can be used in two ways: when the system runs, the user can use copy/paste an example into the input window, then click "OK" to run the example as instructions. In this process, the output lines and the stamps will be ignored. The user can also load a complete example file by choosing it from the Main Window, using "Memory/Load experience". Since the input/output line produced in this way will be quickly overwritten in the display area, it may be necessary to save it into a file, using "Memory/Save experience". The first time this item is selected, the user can open a (new or existing) file to catch the user/system communication. To close the file, select "File/Save experience" again.

The examples are grouped according to the layer they are introduced into NAL:
* [NAL-1: Basic Syntax, Semantics and Inference Rules](https://github.com/opennars/opennars/wiki/NAL-1:-Basic-Syntax,-Semantics-and-Inference-Rules)
* [NAL-2: Derivative Copulas](https://github.com/opennars/opennars/wiki/NAL-2:-Derivative-Copulas)
* [NAL-3: Set-Theoretic Terms](https://github.com/opennars/opennars/wiki/NAL-3:-Set-Theoretic-Terms)
* [NAL-4: Relational Terms](https://github.com/opennars/opennars/wiki/NAL-4:-Relational-Terms)
* [NAL-5: Statements as Terms](https://github.com/opennars/opennars/wiki/NAL-5:-Statements-as-Terms)
* [NAL-6: Variable Terms](https://github.com/opennars/opennars/wiki/NAL-6:-Variable-Terms)
* [NAL-7: Events as Statements](https://github.com/opennars/opennars/wiki/NAL-7:-Events-as-Statements)
* [NAL-8: Operations and Goals as Events](https://github.com/opennars/opennars/wiki/NAL-8:-Operations-and-Goals-as-Events)
* [NAL-9: Self-Monitoring and Self-Control](https://github.com/opennars/opennars/wiki/NAL-9:-Self-Monitoring-and-Self-Control)