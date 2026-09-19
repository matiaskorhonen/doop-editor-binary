# DoopEditor (prebuilt)

Prebuilt macOS XCFramework of [matiaskorhonen/doop-editor](https://github.com/matiaskorhonen/doop-editor). Depending
on this package instead of the source one skips cloning and compiling the 40+ tree-sitter
grammar packages, which are statically linked into the framework.

This repository holds only the generated `Package.swift`. The framework itself is
attached to the [v0.10.1 release](https://github.com/matiaskorhonen/doop-editor/releases/tag/v0.10.1)
of the source repository, and each tag here matches a tag there.

```swift
dependencies: [
    .package(url: "https://github.com/matiaskorhonen/doop-editor-binary.git", from: "0.10.1"),
],
```

The product is the same as the source package's -- `DoopEditor` -- but SwiftPM names a package
after its repository, so switching from source to binary changes the `package:` in the product
reference:

```swift
.product(name: "DoopEditor", package: "doop-editor-binary"),  // was "doop-editor"
```


Generated for v0.10.1 by `Scripts/generate-binary-manifest.swift` in the source repository --
do not edit by hand; changes here are overwritten by the next release.
