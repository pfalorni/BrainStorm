BrainStorm
==========

# M1: Tracking of hand-written text
**Status**: none.

**Input**: coordinate of positions sampled from hand-written text.

**Evaluation**: group points into continous curves in parametric form and calculate the angle of the tangent line at each point.

**Output**: the extracted continuous curve along with the enveloping (minimum) rectangle.
    
    M1.1 = t in [0 T)
    M1.2 = ALPHA(t)
    M1.3 = rect(P1, P2)

# M2: Characters recognition
**Status**: previously unrecognised curves.

**Input**: M1.

**Evaluation**: finds the best match of curves to known characters. Unrecognised curves are stored into internal status.

**Output**: one character along with its enveloping rectangle.

    M2.1 = CH
    M2.2 = rect(P1, P2)
    
