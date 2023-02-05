# V 0.3.3

Release date: 30 Jan 2023

### String interpolation simplified to just `'${name}'`, enforced by vfmt, and updated in the entire code base.
### `[]` is now used for generics instead of `<>`.
### Various ORM fixes and improvements, including string interpolation support, type checks, fn calls in `where`.
### Accessing a pointer map value requires an `or {}` block outside `unsafe`.
### `math.vec` module for generic vector math including 2D, 3D, and 4D vector operations.
### `go foo()` has been replaced with `spawn foo()`.

(launches an OS thread, `go` will be used for upcoming coroutines instead).

### vfmt now supports `// vfmt off` and `// vfmt on` for turning off the formatting locally for short snippets of code.

Useful for keeping your carefully arranged matrices intact.

### fast.vlang.io fixes & improvements, new server.
### New official IntelliJ plugin: https://intellij-v.github.io.
### Lots of fixes in the type checker.
### Match branch range expressions with consts: `match x { const1...const2 {} }`
### Builtin `stb_image.h` used by gg has been updated to the latest v2.28.
### Lots of new language documentation, a nicer table of contents.
### Improved documentation for most of the vlib modules
### All of vlib has been updated to use separate Option/Result types.
### To avoid confusion, all references in the code and documentation to `Optional` have been replaced with `Option`.
### `gg.Context` pipeline has more effects, including the `additive` effect.
### Hot code reloading via `[live]` is now supported in imported modules, not just the main module.
### VFS support in the builtin `sqlite` module; `sqlite.get_affected_rows_count()`.
### `make.bat` & `v up` improvements on Windows.
### Syntax sugar for map inits without needing explicit casts for interfaces: `all.children := { "abc": rect, "def": ui.rectangle()}`.
### `$embed_file()` fixes, including variable args support.
### `none` fixes: no longer allowed to be used as a separate type, `dump()` support, not allowed inside `unsafe`.
### Much cleaner eof checks in `os`: refactor `err == IError(os.Eof{})` to `err is os.Eof`.
### Const functions: `const y = term.yellow`, then `println(y('abc'))`.
### Lots of work on `x.json2`, the pure V json encoder, soon to become official.
### Improved compile time checks, like `$if x is Type {`; `$if T in [$Array, $Struct, $Alias, $Function] {`.
### New `v.reflection` module for runtime reflection.
### Improved `os.mv()`, which now works consistently even across different windows drives/mount points.
### `string.trim_indent()`, useful with multi line strings, that start/end with new lines and indentation.
### Reduced memory consumption in the `crypto` modules.
### Installation instructions for using V on NixOS.
### TeamCity test runner support via `v -test-runner teamcity foo_test.v`.
### Better `make` support for OpenBSD.
### Much improved experience for `v install pcre` on Windows.

It now bundles its own .c files, so it compiles cleanly, even if the platform does not have another pcre package installed.

### Improved `vweb` stability under load.
### Improved `pg` compatibility with older PostgreSQL versions before 2014.
### Native backend: operator support for floats, multi return.
### V can now be compiled with `tcc` on latest macOS and Apple Silicon.
### CI optimizations for faster runs.
### Official V UI library is now licensed under MIT.
### Deprecated `math.util` and `math.mathutil` have been removed.
### Builtin type names can no longer be used as identifiers.
### Generic `typeof[T]()`, `sizeof[T]()`, `isreftype[T]()` functions.
### New official AdventOfCode repo with AOC solutions, also added to CI.
### New time format support: `time.format_rfc3339()`.
### `encoding.html.escape()`.
### Deprecated `-error-limit` in favour of the documented `-message-limit` option.
### Maps now support aliased keys.
### Operator overloading now works with reference types.
### Generic struct inits with nested generic structs and generic optional types are now allowed.
### During array creation, `len:` is required when using default values for the array.
### Optimized one byte `[]u8` arrays creation.
### Int signedness mismatch is now checked: `cannot use literal signed integer as u8`.
### New comptime features for fields: `field.is_<field>`, `field.is_alias`, `field.is_enum`.
### More detailed timings in `v -show-timings`.
### `$for in` works with alias types.
### `v new <name> web` for quickly scaffolding new web projects.
### All public functions in the `hash` and `encoding.base32` modules have been documented.
### Recursive aliasing is no longer allowed (e.g. `type Alias = map[string]Alias`).
### `sqlite`, `pg`, `mysql` have been moved to `db.sqlite`, `db.pg`, `db.mysql`.
### New `crypto.pem` module.
### New `map.reserve()` method.
