# VandalGDB

**VandalGDB** is a pinned fork of [GNU GDB](https://sourceware.org/git/?p=binutils-gdb.git), the GNU debugger, used to build the host and target debugger shipped in the **VandalSDK** toolchain for the **Vandalism Engine** game engine.

This is **not Vandal-authored code**. It is a fork of an existing, independently maintained open-source project, imported here purely so that a specific, known-good version can be built reproducibly as part of the VandalSDK toolchain.

## Baseline

See `VANDALGDB_BASELINE.txt` for the exact upstream commit this fork was taken from.

## Why binutils isn't in this repository

Upstream develops binutils and GDB in the same shared repository, but tags and releases them **independently** — `gdb-17.2-release` and `binutils-2_47` are different commits, not points on one line of history. This repository is pinned to GDB's own official release tag; binutils has its own dedicated fork pinned to its own official release tag: **[VandalBinUtils](https://github.com/chapmanworld/VandalBinUtils)**. Both repositories are forks of the same upstream `binutils-gdb.git`, just pinned at different commits, so each tool is exactly its own stable, officially tagged release.

## Why this repository exists

VandalSDK needs a specific, reproducible GDB build to debug Vandal Engine targets. This fork tracks a single pinned upstream commit while still being able to pull further upstream history at any time via the `binutils-gdb-upstream` remote.

GDB in this toolchain is built against GMP, MPFR, MPC, and ISL — see `VandalGMP`, `VandalMPFR`, `VandalMPC`, and `VandalISL` for those forks.

This repository exists for internal use while building Vandalism Engine and its SDK. It is not a general-purpose GDB distribution.

## Contributions and issue tracking

This is **not a maintained fork**. ChapmanWorld is not accepting contributions here, and this repository is not the place to raise issues, ask questions, or request features.

* Please do not use this repository as a GDB support forum.
* Please do not raise issues here for upstream GDB bugs.
* Please do not use this repository to report Vandal Engine or VandalSDK bugs.
* Issues with GDB itself should be raised with the upstream Sourceware project.

## Licensing

GDB is distributed under the **GNU General Public License (GPL) version 3 or later**, with some components under LGPL variants. See `COPYING3`, `COPYING3.LIB`, `COPYING`, and `COPYING.LIB` in this repository for the authoritative upstream license terms.

## Status

Toolchain dependency fork. Tracks a single pinned upstream commit (`gdb-17.2-release`) for VandalSDK build reproducibility.
