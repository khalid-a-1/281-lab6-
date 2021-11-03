# CS 281: Intro to Computer Systems

## Lab06 – Sequential Circuits, Part II

#### Overview and Objectives

In the last lab, through the prelab and the lab itself, we were introduced to the second major branch of digital
logic design: sequential circuits. We learned the design process steps of

1. Solve the problem with a Finite State Machine, whose states, in general, are annotated with the bits that
are used for system output, and whose transitions are taken based on the system input.

2. Use a collection of clocked 1 bit memory devices, called Flip Flops to remember what ”state” of the
FSM the system is in. This requires, for each state of the FSM, to have a unique bit pattern that is the
state assignment from the FSM state to the 0 and 1 values of the flip flops.

3. Using the techniques of combinational circuits, design a NextState circuit, whose input comes from
both the current saved values of the flip flops (the set of Qi, for subscript i the indices of the set of
flip flops), and from the system inputs that would be on the transitions of the FSM. The output of the
NextState circuit are the control values used to transition the bits of the flip flops.

4. Design an Output circuit, which uses, as input, the state (the Qis) to yield the bits of the system output
desired, as given in the annotations of the FSM. We learned that this output circuit does not require any
information/bits from the system input.

5. For each of the outputs of the NextState circuit and for each of the outputs of the Output circuit, we
arrive at simplified Boolean expressions, typically through the use of K-maps.

6. The circuit is realized by simply putting together the above pieces with a clock and using feedback of
the outputs of the flip flops routed to the NextState circuits and the Output circuits, and the outputs of
the NextState circuits routed to the control inputs of the flip-flops.

Objectives: The objective of this Lab is to reinforce and practice the above design process, building on the
last lab. In particular, we want:

* A FSM that requires more than four states, and so requires more than two flip flops.

* With n flip flops, a total of 2^n patterns representing states are possible. But if our FSM has 2^n-1 < S <
2^n states, we end up with rows in our NextState circuit truth table filled with Don’t Care X entries. Our
design needs to properly handle such Don’t Care entries.

* Learn about a simpler, but less capable flip flop – the D flip-flop. The advantage of the D flip flow is that
it has only one control input (named D), which is the 0 or 1 value for the flip-flop to store in its one-bit
memory. The disadvantage of the D flip flop is that we lose the control-ability of a ”command” to stay
at the same value, or to toggle the value.

* Use logisim to build subcircuits. In this case, we want a subcircuit for the NextState circuit to help keep
our top-level design (in main) clearer.

# For more information, read Lab06__Copy_.pdf
