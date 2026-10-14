# Temporary immutable merge-view module

This module is based on libopenapi v0.41.6, commit
`c4c4be74abe32f0201f6f3086a951178975b00e3`, with the immutable YAML merge-view
fix proposed in [upstream pull request #658](https://github.com/pb33f/libopenapi/pull/658).
The fix prevents model builders from modifying shared YAML mappings while
concurrent readers are using them. It preserves merge precedence, inherited
fields and extensions, and original field source metadata.

The module path and its internal imports are `github.com/CaliLuke/libopenapi`
so applications can fetch this source as an ordinary versioned dependency,
without requiring a replacement directive in each consuming main module.
No additional behavior changes are intended.

Return to `github.com/pb33f/libopenapi` when a stable upstream release contains
the immutable merge-view fix and the merge, metadata, rendering and race
regressions pass against that release. The two module paths declare distinct Go
types; consumers must use one path consistently at any shared type boundary.
