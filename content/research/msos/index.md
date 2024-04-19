---
title: MSOS
date: 1999-12-31
description: A modular variant of SOS (structural operational semantics).
tags:
- SOS
- modularity
- labeled transitions
- operational semantics
---

MSOS (Modular SOS, 1999–2016) is modular variant of SOS (structural operational semantics).

An MSOS is a labelled transition system where states are simply terms
(including computed values),
and labels incorporate all auxiliary entities (e.g., environments, stores, signals),
which can be referenced independently.
Computations require labels on adjacent transitions to be composable.

See the [MSOS in Prolog] project for how to run programs using MSOS rules specified in Prolog.
The [Prolog MSOS Tool] was used in undergraduate courses on formal semantics at Aarhus (2001–2004).

From the first publication about MSOS:

> Modular SOS is a form of SOS that ensures a high degree of modularity:
> the transition rules for each construct are completely independent of the presence or absence of other constructs in the described language.
> When one extends or changes the described language,
> the description can be extended or changed accordingly,
> without reformulation –
> even though new kinds of information processing may be required.
> 
> This is in marked contrast to conventional SOS,
> where modularity tends to be quite poor:
> when extending a pure functional language with concurrency primitives and/or references, for instance, 
> the original specification of the transition rules has to be completely reformulated.
> 
> In denotational semantics, the problem of obtaining good modularity has received much attention,
> and has to a large extent been solved by introducing so-called monad transformers.
> Modular SOS provides an analogous solution for operational semantics.
> 
> The basic idea of Modular SOS is to incorporate all semantic entities as components of labels.
> Thus configurations are restricted to syntax and computed values.
> The foundations of Modular SOS involve a novel form of labelled transition system (LTS),
> where **the labels are the arrows of a category**.
> 
> In contrast to other frameworks where labels are equipped with categorical structure
> (e.g. Tile Logic and Rewriting Logic),
> composition here is generally a partial operation,
> and computations are restricted to those where all adjacent labels are composable.
> Note that the labels are no longer the simple atomic actions often used in studies of process algebra,
> but here usually have entities such as environments and stores as components;
> so do the objects of the label category,
> which correspond to the states of the processed information.
>
> Three fundamental label transformers have been identified;
> they preserve the computations specified by a modular SOS,
> and their order of application is irrelevant.
> The label transformers are analogous to some simple monad transformers.
> 
> - The one which transforms the label category to incorporate new context information
> (such as the current environment) adds the same sort of component both to arrows and to objects,
> and composition preserves the value of that component.
> - Also the transformer which incorporates mutable information
> (such as the current store) adds a corresponding component to each object,
> whereas it extends each arrow with a pair of such components;
> composition on pairs is as for binary relations.
> - Finally, the transformer which incorporates emitted information
> (such as synchronization signals) adds a corresponding component to each arrow,
> but leaves the objects essentially unchanged.
>
> --- <cite>[Foundations of Modular SOS] ([preprint])</cite>

MSOS allows the semantics of individual programming constructs to be specified independently,
which is of crucial importance for the [PLanCompS] project.

### I-MSOS

I-MSOS (Implicitly-Modular SOS) allows the use of conventional SOS notation in MSOS:
specifications use explicit labels only for emitted information,
and the label components for any contextual and mutable information are left implicit.

The [CBS] meta-notation for component-based semantics incorporates an combination of I-MSOS and term rewriting.

[PLanCompS]: ../plancomps/
[CBS]: ../cbs/
[Foundations of Modular SOS]: https://doi.org/10.1007/3-540-48340-3_7
[preprint]: https://www.brics.dk/RS/99/54/BRICS-RS-99-54.pdf
[MSOS in Prolog]: ../../software/msos-in-prolog/
[Prolog MSOS Tool]: ../../software/prolog-msos-tool/
