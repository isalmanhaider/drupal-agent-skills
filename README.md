# Drupal Agent Skills

Agent skills for Drupal projects, built to fill the gaps in what is already
available. They work in Claude Code, Cursor, Codex and any other agent that
reads the [Agent Skills](https://agentskills.io) format.

> **Status:** in development. No skills are released yet.

## Planned skills

### First release

| Skill | What it does |
|---|---|
| `drupal-pr-review` | Reviews a GitHub pull request on a Drupal project, including config-only changes and the deploy steps in the PR description, and starts its report with a verdict. Read-only: it never writes to GitHub. |
| `drupal-project-context` | Scans a Drupal project and writes an `AGENTS.md` describing its sites, environments, config handling and deploy process, so any agent starts informed. |

### Later

- `drupal-site-ci`: a CI pipeline for a Drupal site project.
- `drupal-multisite`: working safely in a codebase that serves several sites.
- `drupal-backlog-triage`: what is waiting on you, what is overdue, and
  which pull requests would close it.

## Quality bar

Every skill in this repository:

- passes the Agent Skills format checks;
- keeps its SKILL.md under 500 lines, with long checklists in reference files;
- works in any agent, with Claude Code-only features as optional extras;
- is tested against sample cases in this repository and must keep passing
  them.

## Install

Once the first release is out:

```
npx skills add isalmanhaider/drupal-agent-skills
```

## License

[MIT](LICENSE)
