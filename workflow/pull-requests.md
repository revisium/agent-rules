# Pull requests

- Submit repository changes through a task branch and a PR. Do not commit or push
  directly to the default branch. Discover the remote's default branch rather than
  assuming main or master; use a requested base branch when specified.
- Start a new task branch from the freshly fetched requested base, unless the
  task explicitly continues existing work. Preserve other branches and checkouts.
- Follow applicable local worktree setup and cleanup instructions. This shared
  guide does not grant consent to create worktrees or install local infrastructure.
- Preserve unrelated staged, unstaged and untracked work. Do not reset, stash or
  overwrite it to make the task's checks or branch setup easier.
- Run the repository's required verification before committing and before handoff.
  Stage only the files belonging to the task and review the staged diff.
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
