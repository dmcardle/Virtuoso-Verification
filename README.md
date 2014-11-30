# Automatic Virtuoso Testing

The goal of this project is to automatically verify the behavior of a schematic
created in Cadence's Virtuoso, using the SKILL language.

## Concept

The main idea is that the user should design a function in SKILL that defines
the expected behavior of a circuit. The circuit will be simulated for all input
patterns and the result of the simulation should be compared to the expected
behavior.

For example, `targetFunc` from `kogge.ils` defines the expected behavior of the
Kogge-Stone adder. The circuit takes two four-bit inputs and a carry-in bit.
The expected behavior is simply the sum of A, B, and the carry-in bit.  We
define the operation in SKILL by converting from bitlists to integers, using
the builtin addition operator, and converting the result back to a bitlist.

    (defun targetFunc (a0 b0 a1 b1 a2 b2 a3 b3 cin)
        A = (list a0 a1 a2 a3)
        B = (list b0 b1 b2 b3)
        Cin = (list cin)
        outputInt = (intValue A) + (intValue B) + (intValue Cin)
        (explodeToBits outputInt))



## Example Usage

To test the Kogge-Stone adder, open Virtuoso's command window and type
`load("kogge.ils")`.

## Remaining work

- [ ] Automatically generate simulation configuration files
- [ ] Find a way to silence the simulation output
- [ ] Improve speed! Use bit-patterns simulation rather than design variables.
