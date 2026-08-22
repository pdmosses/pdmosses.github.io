---
title: Agda-Pages
date: 2026-08-01
description: From the project website.
tags:
- code navigation
- websites
- Agda
---

*Agda* can generate highlighted, hyperlinked HTML pages from a root module,
automatically generating a separate page for each imported module. But it is
left to the user to incorporate the generated pages in a website, and to
publish the website.

*[Agda-Pages]* provides `make` commands to automate the steps that Agda leaves
to the user. The [User Guide] explains how to use Agda-Pages to generate and
publish a website with highlighted listings of your (plain and/or literate)
Agda source files. The [Agda-Pages Demo] website illustrates the appearance
of a website produced using Agda-Pages; the repository illustrates how to
organize the required files and configure the website navigation.

{{< alert >}}
*Agda-Pages* supersedes *Agda-Material!*
{{< /alert >}}

Development of *[Agda-Material]* terminated in July 2026.
*Agda-Pages* is based on the same principles as *Agda-Material*,
but incorporates some significant simplifications. It also avoids the
dependencies on the unmaintained *MkDocs v1.x* website builder and
the *Material for MkDocs* theme.

## Features

*Agda-Pages* generates websites with the following features.

-   **Navigation**:
    each page has a navigation panel for browsing the module hierarchy,
    and shows the path from the root module to the current page.

-   **Hyperlinks**:
    in the listing of an Agda module, clicking on any name jumps to its
    declaration.

-   **Highlighted occurrences**:
    hovering over a name highlights *all* its occurrences in the listing.

-   **Light or dark**:
    users can toggle between light, dark, and automatic color palettes.

-   **Responsive**:
    the page layout adjusts to support browsing on mobile devices as well as
    desktop displays.

-   **Versioning**:
    when multiple versions of a website have been published, a version can be
    set as the default, and users can switch between versions in the browser.

-   **Search**:
    entering a word in the search box displays potential completions, and lists
    links to all pages that contain the word.

## Examples

The **[Agda-Pages Demo]** website illustrates and tests use of Agda-Pages.
The [Demo] section lists the Agda files included in the repository; the
[Library] section lists the many files imported by the included modules.

The following websites were originally generated with [Agda-Material template].
Their development involved editing a large Makefile copied from the template,
with manual updates of the copied Makefile for new releases of Agda-Material.

The [Agda-Pages repository] supersedes the Agda-Material template. When it is
added as a submodule, a simple Git command updates all its files to the latest
commit.

The websites listed below have already been refactored to use Agda-Pages instead
of the files copied from the [Agda-Material template].

### Denotational semantics in Agda

The [XDS-Agda] website includes experimental Agda embeddings of three separate
denotational definitions. The different versions of the website show how the
embeddings have evolved.

### Agda standard library

The [Agda-StdLib] website is a prototype generated from the same Agda files as
the official [Standard Library] webiste. Different versions will correspond to
released versions of the library, and show how the library has evolved.

### TypeTopology Pages

The [TypeTopologyPages] website is a prototype of an alternative rendering of
the official [TypeTopology] website, and is unversioned.

[Agda-Pages]:             https://pdmosses.github.io/agda-pages/
[User Guide]:             https://pdmosses.github.io/agda-pages/User-Guide/

[Agda-Material]:          agda-material/index.md
[Agda-Material template]: https://github.com/pdmosses/agda-material/
[Agda-Pages repository]:  https://github.com/pdmosses/agda-pages/

[Agda-Pages Demo]:        https://pdmosses.github.io/agda-pages-demo/
[Demo]:                   https://pdmosses.github.io/agda-pages-demo/Demo/
[Library]:                https://pdmosses.github.io/agda-pages-demo/Library/
[Agda-StdLib]:            https://pdmosses.github.io/agda-stdlib/pages/master/
[TypeTopologyPages]:      https://pdmosses.github.io/TypeTopology/
[XDS-Agda]:               https://pdmosses.github.io/xds-agda/dev/

[Standard Library]:       https://agda.github.io/agda-stdlib/
[TypeTopology]:           https://martinescardo.github.io/TypeTopology/
