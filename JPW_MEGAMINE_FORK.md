# JPW MegaMine Citizens maintenance fork

This branch is pinned to Citizens build 4120's upstream source revision
`10acd30a8458ec2e0c65e8eeecfb02bb29620aef` for Paper 1.21.8 (`v1_21_R5`).

The only runtime compatibility change restores
`TraitFactory.deregisterTrait(TraitInfo)` and its implementation. ItemsAdder 4.0.17 invokes
that API during plugin shutdown. The implementation is a direct backport of the method from
upstream Citizens2 commit `80dea5239c26e31f3a6b390765d380c207768341` without adopting the
incompatible 26.1 runtime.

The API dependency is the JPW CitizensAPI branch based on the exact API revision bundled by
build 4120, `8e9413845589307efdba331f34d026075dd9717c`, plus that single restored method. Build
and install CitizensAPI `2.0.41-jpw.1` before building this repository.

Citizens remains licensed under OSL-3.0. This fork is maintained solely for MegaMine's
Paper 1.21.8 arena runtime and is not a general upstream release.
