# Rule migration coverage

Source rules: Unliteral Mini App AGENTS.md, REPOSITORY.md and VERIFICATION.md;
Unliteral documentation AGENTS.md and STYLE.md. Shared rules preserve portable
behavior. The listed local owners keep concrete project contracts and settings.
No source repository files are removed or rewritten by this PR. This is a
semantic migration, not a verbatim copy. Intentional adaptations are English as
the shared default, discovering each repository's base branch, and selecting the
existing package manager instead of requiring pnpm in every project.

Additional code/test principles and Git safeguards come from the existing accepted
personal guidelines. Machine-specific worktree paths, registry setup, provider
routing and CodeGraph installations are not made organization requirements.

## Mini App AGENTS.md

| Source rule | Owner after adoption |
| --- | --- |
| Product requirements REQ-008 and UX-002; locate documentation checkout from worktrees | Local AGENTS.md keeps exact documents and workspace lookup |
| Read REPOSITORY.md and VERIFICATION.md | Shared AGENTS.md |
| Components render and wire events; view models own state/actions/lifecycle; services own IO | stacks/react-mobx-fsd.md |
| Composition registration and constructor injection; useViewModel/useService hooks | Stack profile; local REPOSITORY.md fixes src/composition.ts and exact APIs |
| ObservableRequest and abort on disposal | Stack profile; local REPOSITORY.md selects the existing primitive |
| FSD direction and public index.ts | Stack profile |
| One component per file and named props interface | Stack profile |
| Theme tokens, shared/ui/kit and product UI above shared | Stack profile; local REPOSITORY.md fixes primitive paths |
| pnpm, checked-in lockfile and pnpm verify before committing | Shared toolchain/verification policy; local files retain pnpm and pnpm verify |
| Check integration design before new backend endpoints, authentication or GraphQL schemas | Shared contract policy; local AGENTS.md retains the Mini App integration reference |
| Kubernetes configuration in infrastructure repository | Shared boundary policy; local AGENTS.md identifies the repository |
| PR to master, no direct pushes, merge left to user | workflow/pull-requests.md; Mini App's actual base remains master |
| English PR description and local template | Shared English default and template policy; local language overrides can intentionally change it |

## Mini App REPOSITORY.md

| Source area | Owner after adoption |
| --- | --- |
| Current scaffold scope, features not yet implemented and backend calls not yet connected | Local REPOSITORY.md |
| React/TypeScript/Router/Chakra/MobX/DI/FSD baseline and declared tools | Local REPOSITORY.md plus optional stack profile |
| Pinned Node.js/pnpm, lockfile and no tooling migration | Local version declarations plus shared toolchain policy |
| Revo-specific code excluded; retained human copyright and license | Local scope/license declarations plus shared attribution policy |
| Telegram calls, version fallback, safe areas, SDK loading and browser behavior | Local host integration contract |
| Directory layout, exact hooks and independent modules | Local paths plus shared stack boundaries |
| Introduce entities/features with their first slices | Stack profile |
| UI baseline is not approved product design; remaining host/theme work | Stack profile plus local UX and current-state details |
| Backend proxy behavior, authentication verification and no client secrets | Local API/host contract plus shared contract and credential policy |
| Static image runtime, caching, health and API behavior | Local build/runtime contract |
| CI, build, release, deploy and infrastructure ownership | Local workflow configuration plus shared verification and infrastructure policy |
| Sonar token, mandatory gate, scan ownership and deliberate exclusions | Local analysis configuration plus shared quality-gate policy |
| Release tags, release app, dry runs and deployment prerequisites | Local release/deployment configuration plus shared prerequisite policy |

## Mini App VERIFICATION.md

| Source rule | Owner after adoption |
| --- | --- |
| pnpm verify before handoff/commit; format, strict types, zero-warning lint, FSD, coverage and SPA build | Shared required-gate policy; exact command and components remain local |
| pnpm install --frozen-lockfile | workflow/verification.md plus local package manager declaration |
| Async primitive, DI lifecycle and Telegram test coverage | Local verification scenarios; shared behavior-testing policy |
| Avoid duplicate framework tests; browser-check presentation/view models; add domain/transport tests as contracts appear | Shared verification and stack profile |
| Client index and hashed assets present; no server build | Stack profile plus local output paths |
| Narrow viewport, hydration and no console error | Stack profile plus local welcome-screen expectations |
| Close disabled in browser; SDK ready/expand/fullscreen/close and version condition | Local verification scenarios; shared host-stub/browser checking policy |
| Safe-area simulation and real Telegram check once configured | Local host verification scenarios; stack profile |
| Build/run container; health, root, deep link, missing asset and API responses | Shared container checking policy; exact commands and expected responses remain local |
| nginx -t and actionlint when available | Shared configuration/workflow validation policy; nginx command remains local |
| Mandatory SonarCloud gate and token; CI owns scan, automatic analysis disabled | Shared gate policy; local Sonar setup and ownership remain intact |
| Initial stable tag matches package; existing release app; dry_run=true | Shared prerequisite/dry-run policy; local exact release settings |
| DEPLOY_ENABLED and KUBE_DEPLOYMENT after infrastructure is ready | Local deployment prerequisites |

## Documentation AGENTS.md

| Source rule | Owner after adoption |
| --- | --- |
| Current Unliteral series, REQ-001 start, current document links | Local product-series selection plus workflow/documents.md |
| Concise requirements, general to specific | workflow/documents.md |
| ADR decision/API/algorithms linked to requirements; full method descriptions | workflow/documents.md |
| data/, one file per table, Revisium examples/JSON paths, no separate JSON Schema; Prisma/DBOS templates | workflow/documents.md |
| Optional SPEC for large ADRs; parent/REQ/data links; no implementation structure or related-ADR lists | workflow/documents.md |
| UX interaction and business rules agreed in REQ first | workflow/documents.md |
| Requirement IDs, draft renumbering, frozen agreed IDs, references and no reuse | workflow/documents.md |
| Plan order/status/links without requirement copies | workflow/documents.md |
| Explicit Crit request, commit/push agreed round on authorized branch, merge separately | workflow/documents.md |
| Handoff prompts/logs outside repo; no secrets, runtime paths or dialogue logs | workflow/documents.md |
| Link/ID checks and git diff --check | workflow/documents.md |
| STYLE, REQ/ADR/SPEC templates, system-analysis process and catalog | Shared conditional style/workflow loading; local exact templates/process paths |

## Documentation STYLE.md

All original sections are covered in the README's original style coverage table:
common principles, natural technical writing, machine contracts, REQ structure,
interface text and publication checks. Russian wording remains in STYLE_ru.md;
English equivalents are in STYLE_en.md. Unliteral's Russian documentation default
is an explicit local language override, and its glossary/Telegram rules are in
styles/projects/unliteral.md.

## Adoption checks

- Preserve all entries marked local, including exact commands and product contracts.
- Remove duplicated defaults only after checking this mapping and the shared files.
- Make deliberate changes, such as a PR-language exception, explicit in local AGENTS.md.
- Verify conditional profiles load for the intended output and do not migrate other stacks.

## Verification scenarios

| Local selection | Expected result |
| --- | --- |
| No language override | English artifacts; common style plus STYLE_en.md |
| Russian PR titles and bodies | Russian PRs; other artifacts remain English |
| English title, Russian body | Each output loads common style plus its own language profile |
| Russian product documentation only | Russian product docs; English PRs and commits |
| Another language | Common style; no English/Russian language substitution |
| A different local requirement format | Local format wins over styles/requirements.md |
| No selected documentation workflow | No REQ/ADR/data/SPEC workflow imposed |
| No selected Unliteral profile | No Telegram pilot or Unliteral glossary rules imposed |
| A different frontend stack | No React/MobX/FSD migration required |
| Missing shared file | Report before dependent changes; no silent stale fallback |
| Shared branch changes during a task | All shared topic files stay on the task's selected commit |
