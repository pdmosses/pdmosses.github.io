---
title: SIS
date: 1981-12-31
description: A system for running programs according to their denotational semantics.
tags:
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
and ported to several operating systems.

My [dissertation] (1975) describes an early version of SIS.
The SIS [Reference Manual] and [Tested Examples] document the final version.

[dissertation]: https://ora.ox.ac.uk/objects/uuid:b590173b-0a86-40c0-8e75-6a6fc5035c43
[Reference Manual]: ../../papers/Mosses1979SRM.pdf
[Tested Examples]: ../../papers/Mosses1979STE.pdf
