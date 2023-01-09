mynotes_mp_2023-01-08c.md
=========================

# Default Intro to Notes
## My Distribution
### Maintainer License Information

More information at [File: ../MAINTAINER.md](../MAINTAINER.md) in this repository.

### Back to MP Minetest

My notes on general Minetest port development found at
[File: ../MyNotes_MP_Minetest.md](../mynotes_mp_minetest.md)

### Back to the Top

The cover page and introduction found at [File: ../README.md](../README.md).


My Notes from 2023-01-08
========================

## Pull Request(s)

PR [#17258](https://github.com/macports/macports-ports/pull/17258)

## The Backlog & Improve

IMO the MacPorts Guide could improve from general quality assurance and several actions as follows.

**WIP** - This PR and Commit could become a **standing document** until further notice, I presume.

This PR might not be fully compatible to but certainly is related to [7.5. Updating Documentation](https://guide.macports.org/#project.docs)

### Amend

Amending **missing content** at:

#### New section on 'subport'

AFAIK the [Chapter 4. Portfile Development](https://guide.macports.org/#development) lacks sufficient documentary on the 'subport' excellent opportunities both for new Portfile development and port mainentance, unfortunately.

#### section [4.7. Portfile Best Practices](https://guide.macports.org/#development.practices)
  - [4.7.2. Don't Overwrite Config Files](https://guide.macports.org/#development.practices.dont-overwrite)
    TODO:
  - [4.7.3. Install Docs and Examples](https://guide.macports.org/#development.practices.install-docs)
    TODO:
  - [4.7.4. Provide User Messages](https://guide.macports.org/#development.practices.provide-messages)
    TODO:
  - [4.7.5. Use Variables](https://guide.macports.org/#development.practices.use-variables)
   TODO: Set variables so changing paths may be done in one place; use them anytime it makes updates simpler: `distname ${name}-src-${version}`

#### section [6.1. File Hierarchy](https://guide.macports.org/#internals.hierarchy)
  > [PORTHIER](https://guide.macports.org/#porthier)
  > — layout of the ports filesystems
  > Name
  > porthier — layout of the ports filesystems

#### harmonisation of sections 7.1 & 7.3

##### section [7.1. Using Trac for Tickets](https://guide.macports.org/#project.tickets)

> The MacPorts Project uses a system called [Trac](https://trac.macports.org/) to file tickets to report bugs and enhancement requests. Though anyone may search Trac for tickets, you must have a [GitHub account](https://github.com/join) in order to login to [Trac](https://trac.macports.org/) to create tickets.

ADD: _The GitHub pull request method is strongly preferred over submitting Trac tickets._

##### section [7.3. Contributing to MacPorts](https://guide.macports.org/#project.contributing)
> You may contribute new ports and enhancements of any kind to already existing ports using Trac tickets. However, we prefer that you open a pull request on [GitHub](https://github.com/macports/macports-ports/pulls), in which case no Trac ticket is required.
>
> **The GitHub pull request method is strongly preferred over submitting Trac tickets. Submitting a Pull Request will likely result in your contribution being merged into MacPorts much faster, as the workflow is much easier for the maintainers.**

#### Extend 8. Glossary from the utter stub

##### [Chapter 8. MacPorts Guide Glossary](https://guide.macports.org/#guide-terms)

##### [Glossary](https://guide.macports.org/#glossary)

> This section defines a number of words which may be new to the reader. These are all defined in the context of Macports instead of as general purpose definition.

However, **does not meet the expectations** of the reader who would welcome a true glossary and not a stub with a list of terms mostly if not all remaining rather unexplained.

#### TBD

TBC

