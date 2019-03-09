## Text I/O

## Vision I/O
OpenNARS comes with a prototype implementation of a vision channel using the sensory terms (and perceptive terms partly implemented) as presented in our publication "Perception from an AGI Perspective" (https://cis.temple.edu/~pwang/Publication/perception.pdf).
The vision takes in events talking about the brightness level of pixels at given coordinates:
<{M3[x,y]}  --> [bright]>. %b;0.9%
where x and y are the x and y-coordinate each going from -1 to 1, and b encodes a brightness level between 0 and 1 as a truth frequency value.
Once an event for each input pixel have been received, or a pre-defined duration of time has passed, the brightness information that was gained by the vision channel will be summarized into a 2D truth value matrix {MNew}, a so called sensory term. This sensory term represents a prototype that will be matched to the existing stored prototypes {M_i} by pixel-by-pixel based comparison using induction and comparison truth function, summarizing all the obtained truth values with revision obtaining TruthMatch. The closest prototype will then be entered as
<{MBestPrototype} --> [bright]>. TruthMatch 
and the budget (so far just a amount of occurrence counter) of {MbestPrototype} will be increased.
Also {MNew} will be entered as a prototype with initial budget (so far initial amount of occurrence counter 1), kicking out the prototype with the lowest priority (so far with the lowest amount of occurrences), giving {Mnew} the chance to become a useful prototype on its own sake. This principle is shared with Adaptive Neuro-Symbolic Network agent ANSNA, and extending the principle with the adaptation of prototypes similar to https://github.com/patham9/ANSNA/wiki/Concept:-Conceptual-Interpolation will be a future topic.
Additionally in OpenNARS-Lab there exists a Webcam example in the Launcher that demonstrates the use of perceptive terms, that is, sensory terms with a focal point that can be moved by operator invocation.

