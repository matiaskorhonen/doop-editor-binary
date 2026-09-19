# DoopEditor (prebuilt)

Prebuilt macOS XCFrameworks of [matiaskorhonen/doop-editor](https://github.com/matiaskorhonen/doop-editor). Depending
on this package instead of the source one skips cloning and compiling the 40+ tree-sitter
grammar packages, which are statically linked into `CodeEditLanguages`.

This repository holds only the generated `Package.swift`. The frameworks themselves are
attached to the [v0.9.0 release](https://github.com/matiaskorhonen/doop-editor/releases/tag/v0.9.0)
of the source repository, and each tag here matches a tag there.

```swift
dependencies: [
    .package(url: "https://github.com/matiaskorhonen/doop-editor-binary.git", from: "0.9.0"),
],
```

The products are the same as the source package's -- `CodeEditSourceEditor`,
`CodeEditTextView` and `CodeEditLanguages` -- but SwiftPM names a package after its repository,
so switching from source to binary changes the `package:` in each product reference:

```swift
.product(name: "CodeEditSourceEditor", package: "doop-editor-binary"),  // was "doop-editor"
```

These frameworks ship too, because their types appear in the three modules' public interfaces
or the modules load them at runtime:

- `Rearrange`
- `TextStory`
- `SwiftTreeSitter`
- `TreeSitter`
- `Internal`

Generated for v0.9.0 by `Scripts/generate-binary-manifest.swift` in the source repository --
do not edit by hand; changes here are overwritten by the next release.
