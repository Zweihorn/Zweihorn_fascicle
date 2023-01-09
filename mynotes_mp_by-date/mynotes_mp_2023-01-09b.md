mynotes_mp_2023-01-09b.md
=========================

# Default Intro to Notes
## My Distribution
### Maintainer License Information

More information at [File: ../MAINTAINER.md](../MAINTAINER.md) in this repository.

### Back to MP Minetest

My notes on general **IrrlichtMT** port development found at
[File: ../MyNotes_MP_Minetest.md](../mynotes_mp_minetest.md)

### Back to the Top

The cover page and introduction found at [File: ../README.md](../README.md).


# My Notes from 2023-01-09

## Pull Request

PR [#17255](https://github.com/macports/macports-ports/pull/17255)

## The `irrlichtmt` replace

Started by text of my [comment](https://github.com/macports/macports-ports/pull/17255#issuecomment-1375277388
and moved here for clarity and better PR readability.

### Rationale:

#### New `irrlichtmt` replace works

The `sudo port -vst install irrlichtmt` replaces to ` irrlichtmt-mt56` nicely:

```
% sudo port -vst install irrlichtmt
irrlichtmt is replaced by irrlichtmt-mt56
--->  Computing dependencies for irrlichtmt-mt56.
--->  Fetching distfiles for irrlichtmt-mt56
--->  irrlicht-1.9.0mt8.tar.gz does not exist in /opt/macports-test/var/macports/distfiles/irrlichtmt-mt56
. . .
--->  Installing irrlichtmt-mt56 @1.9.0mt8_0
. . .
x ./opt/macports-test/include/irrlichtmt/triangle3d.h
x ./opt/macports-test/include/irrlichtmt/SColor.h
x ./opt/macports-test/include/irrlichtmt/IWriteFile.h
--->  Deactivating irrlichtmt @1.9.0mt8_0
--->  Scanning binaries for linking errors
--->  No broken files found.
--->  No broken ports found.
```

OK?

#### Obsolete Portfile `irrlichtmt-mt57` threw an ERROR

The first `sudo port -vst install irrlichtmt-mt57` threw an ERROR

```
% sudo port -vst install irrlichtmt-mt57
--->  Computing dependencies for irrlichtmt-mt57.
--->  Fetching distfiles for irrlichtmt-mt57
--->  irrlicht-1.9.0mt9.tar.gz does not exist in /opt/macports-test/var/macports/distfiles/irrlichtmt-mt57
--->  Attempting to fetch irrlicht-1.9.0mt9.tar.gz from https://fra.de.distfiles.macports.org/irrlichtmt-mt57
. . .
Error: Failed to activate irrlichtmt-mt57: Image error: /opt/macports-test/include/irrlichtmt/CIndexBuffer.h is being used by the active irrlichtmt-mt56 port.  Please deactivate this port first, or use 'port -f activate irrlichtmt-mt57' to force the activation.
    while executing
"throw registry::image-error $msg"
    ("foreach" body line 47)
    invoked from within
"foreach file $imagefiles {
                set srcfile "${extracted_dir}${file}"

                # To be able to install links, we test if we can lst..."
    invoked from within
"registry::write {
            foreach file $imagefiles {
                set srcfile "${extracted_dir}${file}"

                # To be able to instal..."
Error: See /opt/macports-test/var/macports/logs/_private_var_tmp_devtest_ports_devel_irrlichtmt-mt57/irrlichtmt-mt57/main.log for details.
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port irrlichtmt-mt57 failed
```

Not ok...

#### Resolve conflicts

Amend Portfiles to [resolve conflicts](https://github.com/macports/macports-ports/pull/17255/commits/a8c3ad9df2ce16ad29be86bf3903ebca47865e13) respectively.

All ports uninstalled and followed by fresh install runs with Portfile amend respectively.

The new install of amended `irrlichtmt-mt57` went well and the two check installs for amended `irrlichtmt-mt56` and old `irrlichtmt` both fail as expected.

```
% sudo port -vst install irrlichtmt-mt56
Portfile changed since last build; discarding previous state.
--->  Computing dependencies for irrlichtmt-mt56.
Error: Can't install irrlichtmt-mt56 because conflicting ports are active: irrlichtmt-mt57
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port irrlichtmt-mt56 failed

% sudo port -vst install irrlichtmt
irrlichtmt is replaced by irrlichtmt-mt56
--->  Computing dependencies for irrlichtmt-mt56.
Error: Can't install irrlichtmt-mt56 because conflicting ports are active: irrlichtmt-mt57
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port irrlichtmt-mt56 failed
```

Resolved - OK?
