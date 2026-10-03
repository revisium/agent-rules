# Verification

- Follow the repository's VERIFICATION.md and declared checks. Use the existing
  toolchain; keep exact commands and service setup in the repository.
- Install dependencies reproducibly using the declared lockfile. For pnpm, use
  pnpm install --frozen-lockfile unless dependency or lockfile changes are required.
- Run the repository's complete required gate before handoff or commit, including
  its formatting, type, lint, architecture, test, coverage and build checks.
- Preserve required CI and quality gates, including SonarCloud where configured.
  Report unavailable credentials or infrastructure; do not disable gates to obtain
  a passing result. Follow local setup and analysis ownership instructions.
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
- For container changes, build and run the image and check the specified health,
  root, deep-link, missing-asset and API responses. Validate changed server
  configuration with the repository's tools. Exact images, paths and responses
  belong in local VERIFICATION.md.
- For GitHub Actions changes, run actionlint when available. Follow local dry-run
  checks before real releases; retain required tag and deployment prerequisites.
- Report the commands actually run, their results, and any skipped required checks
  with the reason and concrete limitation.
