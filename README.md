# dcl_probe

Reproduces `// ignore:` comments not suppressing dart_code_linter rules when it
runs as an analysis server plugin (top-level `plugins:`).

```sh
dart pub get
dart analyze
```

Expected: no issues, since every diagnostic in `lib/probe.dart` is ignored.

Actual (dart_code_linter 4.4.2, Dart 3.13.7):

```
info - lib/probe.dart:3:7 - File name does not match with first class name.  - prefer-match-file-name
info - lib/probe.dart:5:3 - Avoid using dynamic type.  - avoid-dynamic
info - lib/probe.dart:8:3 - Avoid using dynamic type.  - avoid-dynamic
```
