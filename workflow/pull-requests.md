# Pull requests

- Submit repository changes through a task branch and a PR. Do not commit or push
  directly to the default branch. Discover the remote's default branch rather than
  assuming main or master; use a requested base branch when specified.
- Commit, push and create or update a PR when authorized by the user's task or
  applicable repository workflow. A request to create a PR authorizes those steps.
- Leave merging to the user unless they explicitly authorize it.
- Use the language selected by the shared Language rules and applicable local
  overrides for PR titles and bodies. Follow the repository's PR template when
  present.
- Lead the description with the problem and resulting behavior. Include relevant
  validation and material compatibility or rollout considerations.
- Run applicable checks before handoff. Resolve failures caused by the change and
  report existing failures or unavailable checks accurately. Do not claim checks
  passed without running them.
