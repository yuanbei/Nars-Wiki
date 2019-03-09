## Text I/O

## Vision I/O
OpenNARS comes with a prototype implementation of a vision channel using the sensory terms (and perceptive terms partly implemented) as presented in our publication "Perception from an AGI Perspective" (https://cis.temple.edu/~pwang/Publication/perception.pdf).
The vision channel takes in events talking about the brightness level of pixels at given coordinates:

<{M[x,y]}  --> [bright]>. :|: %b;0.9%

where x and y are the x and y-coordinate each going from -1 to 1, and b encodes a brightness level between 0 and 1 as a truth frequency value.
Once an event for each input pixel has been received, or a pre-defined duration of time has passed, the brightness information that was gained by the vision channel will be summarized into a 2D truth value matrix {M_New}, a so called sensory term. This sensory term represents a prototype that will be matched to the existing stored prototypes {M_i} by pixel-by-pixel based comparison using induction and the comparison truth function, finally summarizing all the obtained truth values with revision obtaining into a single truth value TruthMatch (for the highest TruthMatch truth expectation spatial arrangement offset (ox,oy), for comparison of {M_New} with {M_i}, to achieve translation invariance). The closest prototype will then be entered as

<{MBestPrototype} --> [bright]>. :|: TruthMatch (ox,oy)

into OpenNARS (or the next higher-level sensory channel in the hierachy if such one exists) and the budget (so far just an amount of occurrences counter) of {M_BestPrototype} will be increased.
Also {M_New} will be entered as a prototype with initial budget (so far the initial occurrence counter being 1), kicking out the prototype with the lowest budget (so far simply the prototype with the lowest amount of occurrences) if at full capacity, giving {M_new} the chance to become an useful prototype on its own sake. 

The latter principle is shared with Adaptive Neuro-Symbolic Network agent ANSNA (https://github.com/patham9/ANSNA), and extending the principle with the adaptation of prototypes similar to https://github.com/patham9/ANSNA/wiki/Concept:-Conceptual-Interpolation will be a future topic for improving the vision channel.

Regarding (ox,oy): This meta-information allows other perception operators to build spatial relationships such as <(*,{M_30},{M_10}) --> leftOf>. :|:
meaning the vision channel allows for a equivariant representation rather than just an invariant one, not loosing the information of the absolute position of the match within the sensory channel.

Additionally in OpenNARS-Lab there exists a Webcam example in the Launcher that demonstrates initial use of perceptive terms, that is, sensory terms with a focal point that can be moved by operator invocation. So far the system places its focal point at the areas within the image that change the most, re-identifying patterns it has seen before as well as learning which patterns likely cause others to appear soon.

