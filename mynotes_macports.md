mynotes_macports.md
===================

# My [MacPorts](https://www.macports.org/) funny [FOSS](https://www.debian.org/intro/free) commits

## My Distribution

### Maintainer License Information

More information at [File: MAINTAINER.md](MAINTAINER.md) in this repository.

### My Notes on Specific Ports

Notes from a [poor old sod](https://youtu.be/i19d1QnstsA) of a [FOSS](license.md)
developer and an [imbecile](https://youtu.be/Lzu7f2q2hW4) made
[Maintainer](https://guide.macports.org/#introduction) of [Port(s)](https://ports.macports.org/).

My maintained ports:
- Minetest Port Development - [File: MyNotes_MP_Minetest.md](mynotes_mp_minetest.md) - maintainer
- _tbc?_

My open maintainer contribution:
- IrrLichtMT Port Development - [File: MyNotes_MP_IrrLichtMT.md](mynotes_mp_irrlichtmt.md)
- _tbc?_

My documentary effort:
- MacPorts Guide QA & Documentary - [File: MyNotes_MP_Guide-aDoc.md](mynotes_mp_guide-adoc.md) - _WIP_

### Back to the Top

The cover page and introduction found at [File: README.md](README.md).


My Notes on **[MacPorts](https://www.macports.org/)** in General
================================================================

## Templates and Check Lists

### MacPorts Checklist for PRs at GitHub

This checklist will pop-up by default in the text area of any new PR at the
[MacPorts](https://guide.macports.org/#project.github) GitHub repository.

This very useful MacPorts _default checklist__ for PRs on ports at GitHub was kindly
[provided by the MacPorts developers](https://guide.macports.org/#project.github).
It was copied here to allow easier access (for myself) while working on improving ports,
however without any specific PR context and amended by myself obviously.

_!-- ## Content amended as TEXT of the MacPorts template comes below this delimiter. ## --_

This is the new ${name} port delivering a cutting edge piece of work.
[Why is this **wrong**?](https://trac.macports.org/wiki/CommitMessages)

#### Description

_!-- Note: it is best to make pull requests from a branch rather than from master --_

###### Type(s)
_!-- update (title contains ": U(u)pdate to"), submission (new Portfile) and CVE Identifiers are auto-detected, replace [ ] with [x] to select --_

- [ ] bugfix
- [ ] enhancement
- [ ] security fix

###### Tested on
_!--
Triple-click and copy the next line and paste it into your shell. It will copy your OS and Xcode version to the clipboard. Paste it here replacing this section.
--_
```
sh -c 'echo "macOS $(sw_vers -productVersion) $(sw_vers -buildVersion) $(uname -m)"; \
xcode=$(xcodebuild -version 2>/dev/null); \
if [ $? == 0 ]; \
    then echo "$(echo "$xcode" | awk '\''NR==1{x=$0}END{print x" "$NF}'\'')"; \
    else echo "Command Line Tools $(pkgutil --pkg-info=com.apple.pkg.CLTools_Executables | \
awk '\''/version:/ {print $2}'\'')"; fi' | tee /dev/tty | pbcopy
```

macOS x.y
Xcode x.y / Command Line Tools x.y.z

###### Verification _!-- (delete not applicable items) --_
Have you

- [ ] followed our [Commit Message Guidelines](https://trac.macports.org/wiki/CommitMessages)?
- [ ] squashed and [minimized your commits](https://guide.macports.org/#project.github)?
- [ ] checked that there aren't other open [pull requests](https://github.com/macports/macports-ports/pulls) for the same change?
- [ ] referenced existing tickets on [Trac](https://trac.macports.org/wiki/Tickets) with full URL? _!-- Please don't open a new Trac ticket if you are submitting a pull request. --_
- [ ] checked your Portfile with `port lint --nitpick`?
- [ ] tried existing tests with `sudo port test`?
- [ ] tried a full install with `sudo port -vst install`?
- [ ] tested basic functionality of all binary files?
- [ ] checked that the Portfile's most important [variants](https://trac.macports.org/wiki/Variants) haven't been broken?

_!-- Use "skip notification" (surrounded with []) to avoid notifying maintainers --_

_!-- ## Content as amended TEXT of the MacPorts template closed above this delimiter. ## --_

Please always heed the [Guidelines for Commit Messages at MacPorts](https://trac.macports.org/wiki/CommitMessages)

<!-- ## Content of the MacPorts template comes below this delimiter. ## -->
```
[this space was - left blank - intentionaly, put:
- consise,
- specific,
- focussed
single headline here]

#### Description

<!-- Note: it is best to make pull requests from a branch rather than from master -->

###### Type(s)
<!-- update (title contains ": U(u)pdate to"), submission (new Portfile) and CVE Identifiers are auto-detected, replace [ ] with [x] to select -->

- [ ] bugfix
- [ ] enhancement
- [ ] security fix

###### Tested on
<!-- Triple-click and copy the next line and paste it into your shell. It will copy your OS and Xcode version to the clipboard. Paste it here replacing this section.
sh -c 'echo "macOS $(sw_vers -productVersion) $(sw_vers -buildVersion) $(uname -m)"; xcode=$(xcodebuild -version 2>/dev/null); if [ $? == 0 ]; then echo "$(echo "$xcode" | awk '\''NR==1{x=$0}END{print x" "$NF}'\'')"; else echo "Command Line Tools $(pkgutil --pkg-info=com.apple.pkg.CLTools_Executables | awk '\''/version:/ {print $2}'\'')"; fi' | tee /dev/tty | pbcopy
-->
macOS x.y
Xcode x.y / Command Line Tools x.y.z

###### Verification <!-- (delete not applicable items) -->
Have you

- [ ] followed our [Commit Message Guidelines](https://trac.macports.org/wiki/CommitMessages)?
- [ ] squashed and [minimized your commits](https://guide.macports.org/#project.github)?
- [ ] checked that there aren't other open [pull requests](https://github.com/macports/macports-ports/pulls) for the same change?
- [ ] referenced existing tickets on [Trac](https://trac.macports.org/wiki/Tickets) with full URL? <!-- Please don't open a new Trac ticket if you are submitting a pull request. -->
- [ ] checked your Portfile with `port lint --nitpick`?
- [ ] tried existing tests with `sudo port test`?
- [ ] tried a full install with `sudo port -vst install`?
- [ ] tested basic functionality of all binary files?
- [ ] checked that the Portfile's most important [variants](https://trac.macports.org/wiki/Variants) haven't been broken?

<!-- Use "skip notification" (surrounded with []) to avoid notifying maintainers -->
```
<!-- ## Content of the MacPorts template closed above this delimiter. ## -->
