# Temporary effective YAML index module

This module is based on libopenapi v0.41.8, commit
`1fdef3ebda12fd344e6f5646001ecad84746afc8`, plus
[upstream PR #673](https://github.com/pb33f/libopenapi/pull/673), commit
`72188ec6bbdbd7db6596eba7a12e8f2904b53d1c`.
The correction makes local component references resolve through YAML aliases and
merges, preserves repeated reference occurrences and source metadata, and guards
cyclic mapping and sequence traversal. See
[issue #672](https://github.com/pb33f/libopenapi/issues/672) for the reproduction.

The module path and self-imports are `github.com/CaliLuke/libopenapi` so consumers
can fetch this revision as an ordinary dependency without replacement directives.
The packaging change only renames module/self references, including the Windows
path fixture, and adds this note.

Return to `github.com/pb33f/libopenapi` when a stable upstream release includes
PR #673 and passes the effective component, metadata, repeated-reference,
render/reload and race regressions. The module paths declare distinct Go types;
use one path consistently at every shared type boundary.
