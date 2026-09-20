# DoopEditor (prebuilt)

Prebuilt macOS XCFramework of [matiaskorhonen/doop-editor](https://github.com/matiaskorhonen/doop-editor). Depending
on this package instead of the source one skips cloning and compiling the 40+ tree-sitter
grammar packages, which are statically linked into the framework.

This repository holds only the generated `Package.swift`. The framework itself is
attached to the [v0.12.1 release](https://github.com/matiaskorhonen/doop-editor/releases/tag/v0.12.1)
of the source repository, and each tag here matches a tag there.

Release notes live with the source repository too, on its
[releases page](https://github.com/matiaskorhonen/doop-editor/releases).

```swift
dependencies: [
    .package(url: "https://github.com/matiaskorhonen/doop-editor-binary.git", from: "0.12.1"),
],
```

The product is the same as the source package's -- `DoopEditor` -- but SwiftPM names a package
after its repository, so switching from source to binary changes the `package:` in the product
reference:

```swift
.product(name: "DoopEditor", package: "doop-editor-binary"),  // was "doop-editor"
```


## Licensing

DoopEditor is MIT-licensed, and the framework statically links its dependencies -- the tree-sitter
grammars, TextStory, TextFormation, Rearrange, SwiftTreeSitter, TreeSitter and swift-collections --
whose licences (MIT, BSD 3-Clause and Apache 2.0) require their notices to be redistributed with
the binary. Because those packages aren't in this package's dependency graph, a licence scanner
run against an app that depends on this package can't find them on its own.

`LICENSE` therefore carries the complete set: DoopEditor's own MIT licence first, followed by every
bundled dependency's licence in full. Tools that read a package's `LICENSE` verbatim -- including
[LicensePlist](https://github.com/mono0926/LicensePlist) -- pick up all of it from that one file.
`THIRD-PARTY-LICENSES.md` is the same set of notices on its own, with a summary table of what is
bundled at which version.

<!-- Generated for v0.12.1 by Scripts/generate-binary-manifest.swift in the source
repository. Do not edit by hand; changes here are overwritten by the next release. -->
