BrainStormer
==========
In a brainstorming session, BrainStormer is the N+1_th participant that do the hard work of providing details about topics that may emerge. There is no need to feed BrainStormer with suitable questions. BrainStormer identifies relevant topics by reading hand-written notes, searches the web for details and print results on a separate screen. Details may be, for example, the graph of a function, the roots of a polinomial or the bio of a cited person.

#1. Modules for the reorganization of hand-written text
These modules are organised in a layered fashion, where the lower layers feed information to the upper one. Going from lower to upper layers the information become more structured but the original data is preserved. In this model, more points become a curve, more curves become a character and more characters become a compound. Because original information is preserved, it is possible, for example, to emphasize a pice of hand-written text that constitute a particular compound.

## M1: Tracking of hand-written text
**Status**: none.

**Input**: coordinate of positions sampled from hand-written text.

**Evaluation**: group points into continous curves in parametric form and calculate the angle of the tangent line at each point.

**Output**: the extracted continuous curve along with the enveloping (minimum) rectangle.

    M1.1 = t in [0 T)
    M1.2 = ALPHA(t)
    M1.3 = rect(P1, P2)
    M1.4 = L % List of coordinates used to build up the curve

## M2: Characters recognition
**Status**: previously unrecognised curves.

**Input**: M1.

**Evaluation**: finds the best match of curves to known characters. Unrecognised curves are stored into internal status.

**Output**: one character along with its enveloping rectangle.

    M2.1 = CH % The internal representation of the recognised character
    M2.2 = rect(P1, P2) % The enveloping rectangle
    M2.3 = L % The list of curves used to recognise the character
    
## M3: Compound reconstrucion
**Status**: previously unused characters.

**Input**: M2.

**Evaluation**: based on a underlying grammar, the internal status and the input, group characters into a compuond. Examples of compound are:
-   Phrase
-   Diagram
-   Graph
-   Figure

**Output**: a compuond.

    M3.1 = K % Kind of compound
    M3.2 = C % The compuond
    M3.3 = L % List of characters

