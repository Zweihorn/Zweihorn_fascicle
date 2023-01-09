mynotes_mp_2023-01-08b.md
=========================

# Default Intro to Notes
## My Distribution
### Maintainer License Information

More information at [File: ../MAINTAINER.md](../MAINTAINER.md) in this repository.

### Back to MP IrrLichtMT

My notes on general **IrrlichtMT** port development found at
[File: ../MyNotes_MP_IrrLichtMT.md](../mynotes_mp_irrlichtmt.md)

### Back to the Top

The cover page and introduction found at [File: ../README.md](../README.md).


My Notes from 2023-01-08
========================

## Pull Request

PR [#17255](https://github.com/macports/macports-ports/pull/17255)

## The `irrlichtmt` replace

Started by text of a.m. PR and moved here for clarity and better PR readability.

### Addendum

NOTE: The original text of the respective commit will be mandatory.

#### Learning from `python311-devel`

While finding only insufficient documentation on supposed 'subports' there is always the option to learn from port experts and well established ports like 'python' presumably.

So what to learn from something as new as `python311-devel` for my _new deal_ approach?

```
PortSystem 1.0
PortGroup obsolete 1.0

name                python311-devel
replaced_by         python311

version             3.11.0rc2
revision            1

categories          lang
license             PSF

# Can be removed after 2023-10-26
```


#### irrlichtmt (replaced)

So nothing new and we could resolve this like:

- amend Portfile to the below
- provide two new port definitions by:
  1. new port 'irrlichtmt-mt56' with 'irrlicht 1.9.0mt8'
  2. new port 'irrlichtmt-mt57' with 'irrlicht 1.9.0mt9'
- all the fix files in new folder 'files' respectively
- integrates with the new 'minetest56' port family

The new Portfile being:
```
PortSystem          1.0
PortGroup obsolete  1.0

name                irrlichtmt
replaced_by         irrlichtmt-mt56

version             1.9.0mt8
revision            0

categories          devel
license             zlib

homepage            https://github.com/minetest/irrlicht

# Should not be removed and will be regular replaced by MT stable irrlichtmt-mtXX
#
# The new port "irrlichtmt-mt56" provides 'irrlicht 1.9.0mt8' for MT 5.6.1+ ports.
# This should apply in continuity until a more stable MT 5.7.1 would be available.
#
# For the future of this port replacement definition:
# Later the port "irrlichtmt-mt57" would provide 'irrlicht 1.9.0mt9' for MT 5.7.1+ ports.
# Change to `replaced_by irrlichtmt-mt57` after upstream release of MT 5.7.1 and port only.

```
OK?

#### minetest (replaced)

Need for integration with 'minetest' and almost nothing new there and we should resolve this like:

```
PortSystem          1.0
PortGroup obsolete  1.0

name                minetest
replaced_by         minetest56

version             5.6.1
revision            2

categories          games
license             LGPL-2.1+

homepage            https://www.minetest.net

# Should not be removed and will be regular replaced by MT stable as applicable.
#
# By rev3 the port "irrlichtmt-mt56" provides 'irrlicht 1.9.0mt8' for "minetest56" ports.
# This should apply until a more stable MT 5.7.1 would be available.
#
# Rationale:  The Minetest application evidently binds to a specific IrrLichtMT fork version.
# Furthermore, many MT players tend to stick with a certain MT version as long as possible,
# because their obvious goal is having fun in a self-built kingdom inside a MT game world.
# However, due to technical quirks and compatibility issues a migration of a MT game world,
# including virtual assets built by same players for hours or even years, would be risky.
#
# WIP for MT 5.7.1 and only for the future of this port replacement definition:
# Later the port "irrlichtmt-mt57" would provide 'irrlicht 1.9.0mt9' for "minetest57" ports.
```

OK?
