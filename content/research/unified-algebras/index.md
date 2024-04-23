---
title: Unified Algebras
date: 1989-12-31
description: An algebraic specification framework where sorts are themsleves values.
tags:
- algebraic specification
---

The Unified Algebras framework (1988–1992) allows algebraic speciﬁcation of sorts as values.
It was used as the meta-notation for specifying [action semantics].

> A unified algebra is a kind of total homogeneous algebra,
> i.e., a set equipped with some total functions.
> Particular unified algebras represent data types;
> classes of unified algebras represent abstract data types.
> This paper establishes an institution,
> i.e., a logical specification framework,
> for specifying abstract data types as classes of unified algebras.
>
> The carrier of a unified algebra is a distributive lattice with a bottom.
> The functions of the algebra always include the join and meet of the lattice,
> and a constant denoting the bottom of the lattice.
> All functions are required to be monotone with respect to the partial order of the lattice.
>
> The main idea is that the values in the carrier of a unified algebra represent not only elements of data,
> but also classifications of elements into sorts.
> For instance, a unified algebra representing a data type of numbers and lists would have values not only for particular numbers and particular lists,
> but also for the sort of all numbers and the sort of all lists.
>
> The lattice partial order of the carrier represents sort inclusion;
> the join and meet operations represent sort union and intersection.
> The bottom of the lattice represents the empty sort.
> The empty sort, shunned in conventional algebraic frameworks,
> provides a particularly natural way of representing the lack of result of partial operations –
> avoiding the need to introduce special "error" elements.
> Operations need not preserve the empty sort.
> 
> --- <cite>[Unified Algebras and Institutions], §1</cite>

[Unified Algebras and Institutions]: https://doi.org/10.1109/LICS.1989.39185
[action semantics]: ../action-semantics/
