mynotes_mp_2023-01-09a.md
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


My Notes from 2023-01-09
========================

## Pull Request(s)

PR [#17258](https://github.com/macports/macports-ports/pull/17258)

## The `minetest` replace
### Rationale:

Always first do a `port lint --nitpick minetest` to identify typos and caveats in the
Portfile.

Always perforam a _clean install__ by `port -vst install minetest` for good reasons:

```
% sudo port -vst install minetest
minetest is replaced by minetest56
--->  Computing dependencies for minetest56..irrlichtmt is known to fail. Try to install anyway? [y/N]: y

The following dependencies will be installed:  irrlichtmt
Continue? [Y/n]:
--->  Fetching distfiles for irrlichtmt
--->  Verifying checksums for irrlichtmt
--->  Extracting irrlichtmt
--->  Configuring irrlichtmt
Error: irrlichtmt has been replaced by irrlichtmt-mt56; please install that instead.
Error: Failed to configure irrlichtmt: obsolete port
Error: See /opt/macports-test/var/macports/logs/_private_var_tmp_devtest_ports_devel_irrlichtmt/irrlichtmt/main.log for details.
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port minetest56 failed
```

Learning and improving. Amend `port:irrlichtmt-mt56` to the Portfile respectively instead of `port:irrlichtmt`.

Resolve by Portfile amend and do a `port lint --nitpick minetest` to identify typos and caveats
```
% sudo port lint --nitpick minetest56
--->  Verifying Portfile for minetest56
Warning: Line 18 seems to hardcode the version number, consider using ${version} instead
--->  0 errors and 1 warnings found.

% sudo port lint --nitpick minetest56-devel
--->  Verifying Portfile for minetest56-devel
Warning: Line 18 seems to hardcode the version number, consider using ${version} instead
--->  0 errors and 1 warnings found.
```

Try a `port -vst install minetest` by:

```
% sudo port -vst install minetest
minetest is replaced by minetest56
Portfile changed since last build; discarding previous state.
--->  Computing dependencies for minetest56..
Error: Can't install irrlichtmt-mt56 because conflicting ports are active: irrlichtmt-mt57
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port minetest56 failed
```

Clean up before a _clean install_ can happen:

```
% sudo port uninstall irrlichtmt irrlichtmt-mt56 irrlichtmt-mt57
--->  Deactivating irrlichtmt-mt57 @1.9.0mt9_0
--->  Uninstalling irrlichtmt-mt57 @1.9.0mt9_0
```

Make a _clean install__ by `port -vst install minetest` for good reasons:

```
% sudo port -vst install minetest
minetest is replaced by minetest56
--->  Computing dependencies for minetest56..
The following dependencies will be installed:  irrlichtmt-mt56
Continue? [Y/n]:
--->  Fetching distfiles for irrlichtmt-mt56
--->  Verifying checksums for irrlichtmt-mt56
--->  Checksumming irrlicht-1.9.0mt8.tar.gz
--->  Extracting irrlichtmt-mt56
--->  Extracting irrlicht-1.9.0mt8.tar.gz
. . .
x ./opt/macports-test/Applications/minetest.app/Contents/Resources/textures/base/pack/minimap_overlay_square.png
x ./opt/macports-test/Applications/minetest.app/Contents/MacOS/minetestserver
x ./opt/macports-test/Applications/minetest.app/Contents/MacOS/minetest
--->  Scanning binaries for linking errors
--->  No broken files found.
--->  No broken ports found.
```

OK?

Make a _clean install__ by `port -vst install minetest56-devel` and other things as follows:

```
% sudo port -vst install minetest56-devel
--->  Computing dependencies for minetest56-devel.
Error: Can't install minetest56-devel because conflicting ports are active: minetest56
Error: Follow https://guide.macports.org/#project.tickets if you believe there is a bug.
Error: Processing of port minetest56-devel failed


% sudo port deactivate minetest56
--->  Deactivating minetest56 @5.6.1_0+GLES


% sudo port -vst install minetest56-devel
--->  Computing dependencies for minetest56-devel.
--->  Fetching distfiles for minetest56-devel
--->  minetest-5.6.1.tar.gz does not exist in /opt/macports-test/var/macports/distfiles/minetest56-devel
. . .
x ./opt/macports-test/Applications/minetest.app/Contents/Resources/textures/base/pack/minimap_overlay_square.png
x ./opt/macports-test/Applications/minetest.app/Contents/MacOS/minetestserver
x ./opt/macports-test/Applications/minetest.app/Contents/MacOS/minetest
--->  Scanning binaries for linking errors
--->  No broken files found.
--->  No broken ports found.


% port info minetest56-devel
minetest56-devel @5.6.1 (games)
Variants:             [+]GLES, [+]benchmark, debug, gprof

Description:          open source infinite-world block sandbox game with survival and crafting - minetest56-devel provides the minetest 5.6.1 for MT 5.6 devs. Find
                      more MT mods at <https://content.minetest.net/> and have fun.
Homepage:             https://www.minetest.net

Build Dependencies:   cmake, doxygen, mesa
Library Dependencies: irrlichtmt-mt56, libjpeg-turbo, libogg, libvorbis, freetype, gettext, leveldb, sqlite3, zstd, luajit, gmp, curl, jsoncpp, spatialindex,
                      xorg-libX11, xorg-libXxf86vm
Conflicts with:       minetest, minetest56
Platforms:            darwin
License:              LGPL-2.1+
Maintainers:          GitHub: Zweihorn
                      Policy: openmaintainer

```

OK?
