mynotes_mp_2023-01-10b.md
=========================

# Default Intro to Notes
## My Distribution
### Maintainer License Information

More information at [File: ../MAINTAINER.md](../MAINTAINER.md) in this repository.

### Back to MP IrrLichtMT

My notes on general **IrrlichtMT** port development found at
[File: ../MyNotes_MP_IrrLichtMT.md](../mynotes_mp_irrlichtmt.md)

### Back to Cover Page

The cover page and introduction found at [File: ../README.md](../README.md).


My Notes from 2023-01-10
========================

## Pull Request

PR [#17255](https://github.com/macports/macports-ports/pull/17255)

## The `irrlichtmt` amend

Started with my [comment](https://github.com/macports/macports-ports/pull/17255#issuecomment-1375277388

### Rationale:

#### New Deal & New `subport` Approach

My [comment](https://github.com/macports/macports-ports/pull/17255#discussion_r1065955112)
on prior comment by @l2by :

> Unfortunately, there is no official documentation on these topics. You need to learn from other ports that are doing this.

Understood. However, there shall be **subports in one Portfile** to comprise in one port accordingly.

([@l2by](https://github.com/l2dy))

#### The `subport` Approach

Ref https://trac.macports.org/ticket/36957 - Guide: Document the "subport" command

> Usage:
>
> `subport <subname> { body }`
>
> Body is executed if the portfile has been opened as the port name <subname>. This allows defining multiple ports in a single portfile, which avoids redundancy in cases where you would otherwise need to have several almost identical portfiles.

The a.m. reply is 10 years old.  However, nobody found the time for documentary effort since.

#### New `irrlichtmt` Portfile with subports

Ref https://github.com/macports/macports-ports/pull/17255/commits/23a526a293f5deaaa72b163622c3b67187d90761

