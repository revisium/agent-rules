# Common writing style

Apply when writing or editing project prose. The shared AGENTS.md and applicable
local language overrides select each output's language. This guide controls style
and does not change that selection.

## Basic rules

- Each sentence communicates a fact, decision, requirement, constraint or consequence.
- Each paragraph develops one idea.
- Name the actor: the user, system or named role.
- Use active verbs rather than nominalized operations.
- Replace evaluative words with observable behavior.
- Explicitly distinguish hypotheses, accepted decisions, requirements and open questions.
- Use each term consistently across documents.

## Natural technical writing

Write in a neutral professional tone for a colleague who must make a decision or
implement the system. Start with the concrete task, decision or result. Preserve
technical terms and explain those that are not clear from context on first use.

A heading names the subject of its section. For example, "What the decision
changes" is more precise than "Consequences" when describing tables and operations.
After the heading, state which data or actions change.

Replace template questions and prompts with concrete facts. Before review, reread
the document as connected prose in the selected language. Check that the reader
can understand its main point without reading every detail.

## Machine contracts and names

Preserve these in their original form:

- Entity names in technical documents and machine contracts.
- JSON fields and error codes.
- HTTP, API, GraphQL and protocol names.
- Commands, logs and diagnostic messages.
- Technology and provider names.

Preserve code identifiers and quoted source text as well. Keep English example
phrases and names of English grammatical forms in English.
Use the product glossary for business concepts. Apply the selected language's
conventions when building sentences around retained technical terms.

## Interface text

The interface language follows the client's locale and the project's UX rules.
An exact interface label uses code formatting when the string itself is part of
the UX contract. Otherwise, describe the message's meaning; keep the final string
in the implementation or localization catalog.

## Before publication

Reread the whole document. Check:

- Suitability for the document's genre.
- Consistent terminology.
- Absence of repetition.
- Working relative links.
- Sequential numbering.
- Absence of promotional text and incidental implementation details.

Follow local templates and the applicable document profile for structure.
