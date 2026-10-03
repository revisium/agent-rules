# Revisium shared agent rules

These are defaults for repositories that explicitly load this document.

## Precedence and loading

- Follow the agent platform's instruction hierarchy. Within project guidance,
  explicit user instructions take precedence, then applicable repository and
  directory instructions (including local overrides), then these shared defaults.
- Load only the topic files whose conditions below apply. Resolve relative links
  against this document's location: the local directory in this checkout, or the
  corresponding raw GitHub URL when loading remotely.
- When loading remotely, resolve the selected branch to a commit once and load
  this file and its topic files from that commit. Keep that version for the task;
  refresh for a new task. State the shared rules commit in the task handoff.
- If required shared guidance cannot be retrieved, report the missing document
  before making changes that depend on it. Do not silently use an old copy.
- When editing agent-rules itself, read the local files being changed rather than
  fetching the published copy again.

## Language

- Use English by default for written project artifacts, including PR titles and
  bodies, commit messages, issues, and documentation.
- An applicable repository or directory AGENTS.md can override the language for
  all artifacts or named outputs. Apply the exception only to its stated scope;
  outputs not named in a scoped override retain the shared default.
- An explicit user language instruction takes precedence for the requested output.
- Preserve code identifiers, commands, paths and quoted source text. Follow product
  localization requirements for user-facing copy; do not translate existing
  content merely to apply this default.

## Shared behavior

- Read applicable local instructions before changing files. Read REPOSITORY.md
  and VERIFICATION.md when present for architecture, boundaries and checks.
- Preserve unrelated changes. Stage only files belonging to the task.
- Use the repository's declared package manager, lockfile and toolchain. Do not
  migrate tooling or install new project tools without agreement.
- Check agreed requirements and API contracts before changing product behavior,
  authentication, schemas or integration boundaries. Update affected documentation
  with the implementation; surface missing decisions rather than inventing them.
- Keep Kubernetes and deployment resource definitions in the designated
  infrastructure repository; application build files stay with the application.
  Follow local repository boundaries when they differ.
- Do not expose or commit credentials or private local configuration.
- Preserve human attribution. Do not add agent signatures, Co-authored-by entries,
  or promotional boilerplate unless explicitly requested or required by policy.

## Conditional guidance

- Before writing or editing prose in project artifacts, read
  [common writing style](styles/STYLE.md). Select each output's language using
  the Language rules above and applicable local overrides. For English, also
  read [English style](styles/STYLE_en.md); for Russian, also read
  [Russian style](styles/STYLE_ru.md). Load only the selected language profile.
  For another language, apply the common rules; do not substitute English or
  Russian. Style documents do not override the selected language.
- When writing REQ documents, also read
  [requirement document style](styles/requirements.md), unless local instructions
  specify another format.
- Load [Unliteral style](styles/projects/unliteral.md) only when the consuming
  repository explicitly selects it for Unliteral documentation or its Telegram
  RU → EN pilot.
- Before changing a repository or preparing a PR, read
  [pull requests](workflow/pull-requests.md).
- For repositories explicitly selecting the REQ / ADR / data / SPEC / UX
  workflow, read [product documentation](workflow/documents.md) before editing
  requirements, analysis or project documentation.
- Before implementation or code review, read
  [code principles](principles/code.md).
- For behavior changes, tests, or verification, read
  [verification](workflow/verification.md).
- For a repository already using React, MobX/MVVM and Feature-Sliced Design, read
  [React/MobX/FSD](stacks/react-mobx-fsd.md). This profile does not require other
  repositories to adopt that stack.

Keep this entry point short. Add topic rules in separate files with explicit
loading conditions. Keep project-specific commands and paths in their repositories.
