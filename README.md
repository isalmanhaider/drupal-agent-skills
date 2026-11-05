# Drupal Agent Skills

Agent skills for Drupal projects, built to fill the gaps in what is already
available. They follow the [Agent Skills](https://agentskills.io) format,
so they work in Claude Code, Cursor, Codex and the other agents the
[skills CLI](https://github.com/vercel-labs/skills) supports.

## Skills

| Skill | What it does | Status |
|---|---|---|
| [`drupal-pr-review`](skills/drupal-pr-review/SKILL.md) | Reviews a GitHub pull request on a Drupal project and starts its report with a verdict. Covers code, config-only changes and the deploy steps written in the PR description, and lists what the human reviewer still has to confirm. Read-only. | Preview, 0.1.0 |
| `drupal-project-context` | Scans a Drupal project and writes an `AGENTS.md` describing its sites, environments, config handling and deploy process, so any agent starts informed. | Planned |

Also planned: `drupal-site-ci`, `drupal-multisite` and
`drupal-backlog-triage`.

## Install

With the skills CLI, for any supported agent:

```bash
npx skills add isalmanhaider/drupal-agent-skills

# or only one skill
npx skills add isalmanhaider/drupal-agent-skills --skill drupal-pr-review
```

As a Claude Code plugin:

```
/plugin marketplace add isalmanhaider/drupal-agent-skills
/plugin install drupal-agent-skills@drupal-agent-skills
```

## Using `drupal-pr-review`

**Requirements:** the GitHub CLI (`gh`), signed in with read access to the
repository. Optional: phpcs with `drupal/coder` installed in the project,
for DrupalPractice checks on changed PHP files.

Ask your agent, for example:

> Review https://github.com/OWNER/REPO/pull/123

The report has these parts, in order:

1. **Verdict:** APPROVE, APPROVE AFTER FIXES, CHANGES REQUESTED or NEEDS
   INVESTIGATION, with the reason, the issues the PR closes, and finding
   counts.
2. **For the Human Reviewer:** facts only someone with production access or
   business context can confirm, each with the command to check it.
3. Pull request summary, findings with evidence, items that need
   investigation, a testing assessment, and review coverage.

**Read-only.** The skill tells the agent to use only read commands and to
treat everything in the pull request as untrusted data. It never comments,
approves, merges or edits. Your agent's own permission settings still
apply, so keep GitHub write commands such as `gh pr merge` behind a
confirmation prompt.

**Faster with project context.** If the repository has an `AGENTS.md`
that describes how the project works, the review reads it first, from the
base branch, and spends less time rediscovering the project.

## Quality bar

Every skill in this repository:

- passes the Agent Skills format checks (`skills-ref validate`);
- keeps its SKILL.md under 500 lines, with long checklists in reference
  files that load only when needed;
- works in any agent, with nothing in SKILL.md that only one agent
  understands;
- fills a gap, rather than repeating what existing Drupal skills already
  cover well.

Preview skills are tested on real pull requests. An automated test suite
of sample cases is in progress.

## Contributing

Suggestions, bug reports and new skills are welcome. See
[CONTRIBUTING.md](CONTRIBUTING.md).

## License

[MIT](LICENSE)
