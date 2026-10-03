# Verification

- Follow the repository's VERIFICATION.md and declared checks. Use the existing
  toolchain; keep exact commands and service setup in the repository.
- For new behavior and fixes, prefer a readable regression test that fails for
  the expected reason before implementation. Test observable system behavior.
- Reuse existing fixtures and scenario vocabulary. Keep conditions, action and
  expected outcome readable; move transport and database setup into support code.
- Do not add tests for trivial framework delegation, generated code or library
  internals merely to increase coverage. Documentation-only changes need document
  and link checks rather than application runtime tests.
- Use existing green tests for behavior-preserving refactors. Do not break code
  artificially to demonstrate a failing test.
- Run checks appropriate to the changed behavior after the final edit. For UI
  behavior, verify relevant interactions in a browser when available.
- Report the commands actually run, their results, and any skipped required checks
  with the reason and concrete limitation.
