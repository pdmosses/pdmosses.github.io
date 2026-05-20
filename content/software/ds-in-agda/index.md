---
title: Denotational Semantics in Agda
date: 2024-10-25
description: A technique that allows a denotational semantics to be defined straightforwardly in Agda
tags:
- Agda
- denotational semantics
- Scott-domains
---

This project (started in 2024) aims to make it straightforward to take an existing
denotational semantics of a programming language,
and use the Agda type-checker to test its well-formedness.
A secondary aim is to test whether the denotations of individual programs have
expected properties.

## The Problem

A Scott–Strachey style denotational semantics[^1] is based on Scott-domains.
It assumes that a domain is an appropriate kind of cpo,
and defines domains (up to isomorphism) using various domain constructors, allowing mutual recursion.
All functions on domains specified in λ-notation are Scott-continuous,
and endofunctions have least fixed points.

Agda does not assume that types are Scott-domains,
nor that functions specified in λ-notation are continuous.
Some Agda libraries have been developed to support Scott-domains;
but when using them, a domain is represented as a *pair* of a type of elements and other data;
and a continuous function is represented as a *pair* of a function and a proof of its continuity.
These representations give rise to undesirable notational overhead and obfuscation
when specifying elements of domains in λ-notation.

## Experiments

As a novice Agda user, I experimented with a lightweight workaround for this problem, reported in 
*[Towards Verification of a Denotational Semantics of Inheritance](https://doi.org/10.1145/3694848.3694852 "ACM Digital Library")* (JENSFEST 2024),
*[Lightweight Agda Formalization of Denotational Semantics](https://msp.cis.strath.ac.uk/types2025/abstracts/TYPES2025_paper11.pdf "PDF")* (TYPES 2025),
*[Checking a Denotational Semantics of Scheme in Agda](https://doi.org/10.1145/3759537.3762694 "ACM Digital Library")* (SCHEME 2025), and
*[A Compositional Semantics for `eval` in Scheme](https://doi.org/10.1145/3759427.3760369 "ACM Digital Library") *(OlivierFest 2025).

Some experiments with using a simplified version[^2] of the above approach are
documented at https://pdmosses.github.io/xds-agda/.
The experiments currently include Agda formalizations of the denotational semantics of
[the untyped λ-calculus](https://pdmosses.github.io/xds-agda/LC/),
[PCF](https://pdmosses.github.io/xds-agda/PCF/), and
[Scm](https://pdmosses.github.io/xds-agda/Scm/)
(a simple sublanguage of Scheme).
These experiments are reported in
*[Mechanising Denotational Semantics in Agda*](https://ul-fmf.github.io/mfps-sstt-2026/files/pdfs/mfps/MFPS26-17.pdf), with [Jesper Cockx](https://jesper.sikanda.be) and [Bernhard Reus](https://profiles.sussex.ac.uk/p115097-bernhard-reus/) (MFPS 2026),
see the accompanying [website](https://pdmosses.github.io/mfps2026-agda/).


{{< alert "comment" >}}
Comments and suggestions for improvement are welcome!
{{< /alert >}}

The lightweight approach simply assumed that all Agda types are Scott-domains,
and that all Agda functions have fixed points.
Such assumptions are obviously unsound,
but the Agda proof assistant accepted them,
and their unsoundness did not affect checking definitions for well-formedness.

However, it would clearly be better to develop a more principled solution,
based on an implementation of
*[Synthetic Domain Theory](https://ncatlab.org/nlab/show/synthetic+domain+theory "ncatlab page") (SDT)* in Agda.
The assistance of expert Agda users will surely be needed...

[^1]:
    A denotational semantics of a programming language maps programs and their phrases
    directly to their denotations: immutable values -- typically higher-order functions.
    The denotation of a complete program represents its potential behaviour when executed.
    Denotations are compositional: the denotation of a phrase is defined inductively in terms of
    the denotations of its subphrases, independently of their form.
    The denotations of loops and recursive definitions involve fixed points
    of functions on denotations.

[^2]:
    For simplicity, domains are defined to be unordered pointed sets,
    and endofunctions are required only to have well-defined fixed points.
    Postulates corresponding to the intended cpo structure of domains,
    and the continuity of functions between domains, are to be added.