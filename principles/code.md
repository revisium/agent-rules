# Code principles

- Give each class or module one cohesive responsibility. Split by reason to
  change, not by an arbitrary line count.
- Keep methods at one level of abstraction. Express intent with named operations
  and move lower-level details below.
- Give repeated transformations one owner. Prefer a clear if and a named function
  over difficult conditional spreads or nested ternaries.
- Preserve the selected stack's idioms. Introduce dependencies, architectural
  layers and abstractions only for a concrete need and with agreement.
- Use braces for control flow and put the body on separate lines. Separate methods,
  declarations and semantic blocks with blank lines.
- Express intent through names and structure. Use comments sparingly to explain
  non-obvious constraints, rather than narrating the code.
