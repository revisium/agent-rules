# Product documentation workflow

Apply only when local AGENTS.md selects this REQ / ADR / data / SPEC / UX workflow.
Follow local templates and product-specific rules, plus the selected writing style.

## Requirements and decisions

- Start with concise business requirements and discuss them from general to specific.
- Describe user interaction in UX. Agree new business rules in REQ before adding
  them to UX or implementation.
- Requirements use IDs of the form REQ-NNN.BR-NNN. Number draft rules sequentially;
  when reordering, renumber them and update references. Freeze IDs after agreement.
  ADR, SPEC and acceptance checks reference them. Do not reuse deleted IDs within
  the current series.
- Keep links pointing to current documents. Follow local instructions for the
  active product series and its starting REQ number.

## ADR, data and SPEC

- After requirements, write ADRs covering decisions, module APIs and algorithms,
  with references to the requirements.
- Describe each method fully: input, result, algorithm, errors and retries.
- In data/, document tables, fields, relationships and constraints. Use one file
  per table.
- For Revisium, provide an example row and describe fields by JSON path; do not
  keep separate JSON Schema documents. Describe Prisma and DBOS JSON structures
  separately using the applicable local templates.
- SPEC is optional. Move detail into SPEC when an ADR becomes too large. Reference
  the parent ADR, requirements and data/. Do not include classes, decorators or
  implementation structure, and do not add lists of related ADRs.
- Follow the documentation repository's system analysis process and template
  catalog for tables, JSON and review rounds.

## Plan, review and checks

- plan.md contains work order, statuses and links, without copying requirements.
- Use Crit only when explicitly requested by the user. After a substantive agreed
  review round, commit and push the authorized working branch; merging requires
  separate authorization.
- Keep implementation handoff prompts and execution logs outside the repository.
  Do not include secrets, local runtime paths or dialogue logs in canonical docs.
- Before completion, check links, uniqueness of requirement IDs and git diff --check.
