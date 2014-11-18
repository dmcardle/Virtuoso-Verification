# Automatic Virtuoso Testing

The goal of this project is to automatically verify the behavior of a schematic
or layout created in Cadence's Virtuoso.

Code is written in the OceanScript language, a superset of the Lisp-based SKILL
language.

## Example Usage

To test a 1-bit AND function, open Virtuoso's command window and type
`load("and_test.ocn")`.

The output should look like this.

    A = FALSE, B = FALSE, target = FALSE
    success
    A = TRUE, B = FALSE, target = FALSE
    success
    A = FALSE, B = TRUE, target = FALSE
    success
    A = TRUE, B = TRUE, target = TRUE
    success
