# Developer Guidelines

Guidelines for Claude Code when working on this Java codebase.

## Java version

- Before writing code, detect the version in use (check `pom.xml`, `build.gradle`, `.sdkmanrc`, or the `--release`/`sourceCompatibility` setting) and stay within that version's feature set.
- When the target version supports a newer language feature that makes the code simpler or clearer, use it. Do not backport features the project version cannot compile.

## Code style

- Keep code simple and direct. Prefer the shortest readable solution over clever or layered abstractions.
- Do not add comments. Code should be self-explanatory through naming.
- One responsibility per method. Extract a method instead of nesting deeply.
- Fail fast: validate inputs at the top and return/throw early rather than wrapping the body in `if` blocks.
- Prefer immutability: `final` fields, unmodifiable collections, no setters unless required.

## Error handling

- Throw specific exceptions, not bare `RuntimeException`.
- Do not swallow exceptions with empty `catch` blocks.


## Testing

- Only run tests when explicitly asked. Do not run the test suite after every change by default.
- When asked to run tests, use the project's configured runner (`mvn test`, `./gradlew test`).
- When writing tests, keep one assertion focus per test and use clear method names describing the scenario.
