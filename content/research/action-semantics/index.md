---
title: Action Semantics
date: 1985-12-31
description: A meta-language for extensible semantic specification of programming languages.
tags:
- action notation
- modularity
- extensibility
---

Action Semantics (1985–2005) is a hybrid of denotational and operational semantics,
developed in collaboration with [David Watt] (Glasgow).

An action semantics of a programming language maps syntax compositionally to action notation,
and the semantics of action notation is defined using SOS (structural operational semantics).

See the [Wikipedia] page and the [Action Semantics book].

The non-modularity of the original SOS of action notation prompted the development of
[MSOS] (a modular variant of SOS using labeled transitions)
and [I-MSOS] (a version of MSOS using conventional SOS notation).

[David Watt]: https://en.wikipedia.org/wiki/David_Watt_(computer_scientist)
[Wikipedia]: https://en.wikipedia.org/wiki/Action_semantics
[Action Semantics book]: https://doi.org/10.1017/CBO9780511569869
[MSOS]: ../msos/
[I-MSOS]: ../msos/#i-msos
