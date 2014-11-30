# Automatic Virtuoso Testing

The goal of this project is to automatically verify the behavior of a schematic
or layout created in Cadence's Virtuoso, using the SKILL language.

## Example Usage

To test the Kogge-Stone adder, open Virtuoso's command window and type
`load("kogge.ils")`.

The output should look like this.

    A = FALSE, B = FALSE, target = FALSE
    success
    A = TRUE, B = FALSE, target = FALSE
    success
    A = FALSE, B = TRUE, target = FALSE
    success
    A = TRUE, B = TRUE, target = TRUE
    success

## Remaining work

- [ ] find a way to silence the simulation output
