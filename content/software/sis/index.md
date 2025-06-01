---
title: SIS
date: 1981-12-31
description: A system for running programs according to their denotational semantics.
tags:
- SIS
- denotational semantics
- executable semantics
- partial evaluation
- lambda interpreter
- call by need
- BCPL
---

SIS (semantics implementation system, 1972–1979) used partial evaluation
to run programs according to their denotational semantics.

It included an SLR(1) parser generator,
a call-by-need lambda-notation interpreter,
and a translator from denotational semantics specifications to lambda-expressions.

SIS was written in BCPL at Oxford (1972--1976) and Aarhus (1976--1979),
and ported to several operating systems, including MULTICS at MIT.

My initial aim was to use SIS for generating correct-by-construction interpreters
and compilers for programming languages
from their denotational semantics.
However, that turned out to be over-ambitious,
and the main application of SIS was as tool support for teaching denotational semantics
(personally at Aarhus, and by colleagues at universities in some other countries).

Moreover, attempts to develop denotational semantics for larger programming languages
in SIS clearly exposed a significant lack of modularity in the meta-notation.
This led to the development of the [action semantics] framework,
which uses a combination of denotational and operational semantics.

My [dissertation] (1975) describes an early version of SIS.
The SIS [Reference Manual] and [Tested Examples] document the final version (1979).

The SIS code for a denotational semantics of the *ASPLE mini-language*,
by Veronique Donzeau-Gouge, Bernard Lang, and Gilles Kahn,
was published as an [IRIA research report] (1978),
and used in the successful bid for the DoD contract to develop the Ada language.

*[Experimentation with using SIS for compiler generation]* was reported in a SIGPLAN article by
James Bodwin, Laurette Bradley, Kohji Kanda, Diane Litle, and Uwe Pleban (1982).
Peter Lee and Uwe Pleban subsequently developed a *[realistic compiler generator]*, published at POPL (1987). It is based on high-level semantics, which is related to [action semantics].

[dissertation]: https://ora.ox.ac.uk/objects/uuid:b590173b-0a86-40c0-8e75-6a6fc5035c43
[IRIA research report]: https://inria.hal.science/hal-04716568/file/INRIA1978_333_pdf_impression.pdf "PDF"
[Reference Manual]: ../../papers/Mosses1979SRM.pdf "PDF"
[Tested Examples]: ../../papers/Mosses1979STE.pdf "PDF"
[action semantics]: ../../research/action-semantics/
[Experimentation with using SIS for compiler generation]: https://doi.org/10.1145/872726.806997 "ACM DL"
[realistic compiler generator]: https://doi.org/10.1145/41625.41651 "ACM DL"