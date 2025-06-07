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
and use Agda to check its well-formedness,
as well to prove properties of individual programs.

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

As a novice Agda user, I developed a lightweight workaround for this problem, reported in 
*[Towards Verification of a Denotational Semantics of Inheritance](https://doi.org/10.1145/3694848.3694852 "ACM Digital Library")* (2024) and
*[Lightweight Agda Formalization of Denotational Semantics](https://msp.cis.strath.ac.uk/types2025/abstracts/TYPES2025_paper11.pdf "PDF")* (2025).

However, it would clearly be better to develop a more principled solution,
based on an implementation of
*[Synthetic Domain Theory](https://ncatlab.org/nlab/show/synthetic+domain+theory "ncatlab page") (SDT)* in Agda.
The assistance of expert Agda users will surely be needed...

## A Proposed Approach

The idea is to allow named types to be declared to be domains (or predomains).
To avoid extending the syntax of Agda, it has been suggested to me that
a universe `Domain` (hierarchy) could be added as built-in,
although that would require extending the Agda compiler.

When declared to be a domain, an Agda type is to have a partial order with a least element ⊥,
closed (at least) under limits of monotone ascending ω-chains.
All functions between domains are to be Scott-continuous, preserving the partial order and limits;
the limit of the ascending Kleene chain of an endofunction on a domain is then its least fixed point.

Groups of Agda types declared to be domains are to be definable (up to isomorphism)
in terms of flat domains (lifted sets) and built-in domain constructors
(including function domains, Cartesian products, sum domains, lifted domains).
The type of all functions from an ordinary type to a domain may also be treated as a domain,
implicitly ordered pointwise.

Recursive references to domains are *not* to require guards,
and type checking is to allow the isomorphisms between domains and their definitions
to be left implicit when expressing elements of domains in λ-notation.

## Experiments

Some experiments with using a simplified version[^2] of the above approach can be
browsed on web pages or PDFs at https://pdmosses.github.io/xds-agda/.

The experiments currently include denotational semantics of
[the untyped λ-calculus](https://pdmosses.github.io/xds-agda/ULC.html),
[PCF](https://pdmosses.github.io/xds-agda/PCF.html), and
[core Scheme](https://pdmosses.github.io/xds-agda/Scheme.html).

{{< alert "comment" >}}
Comments and suggestions for improvement are welcome!
{{< /alert >}}

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