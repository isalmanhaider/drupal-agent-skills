# Contributing

Thanks for helping make these skills better. Contributions of every size
are welcome: a missed finding, a clearer instruction, or a whole new skill.

## Report a missed or wrong finding

This is the most useful contribution. Open an issue with:

- a small **synthetic** diff or snippet that shows the problem (never real
  code from a private project);
- what the skill reported;
- what it should have reported, and why.

Reports like these become test cases, so the skill keeps catching the
problem after later changes.

## Propose a new skill

Before writing one, search [skills.sh](https://skills.sh) for existing
Drupal skills. This repository only adds skills that fill a gap or do
clearly better than what is already there. Open an issue describing:

- the task the skill helps with, and who runs into it;
- what existing skills cover, and what they miss;
- how you would show the skill works.

## Change or add a skill

1. Follow the conventions in [AGENTS.md](AGENTS.md): spec-only
   frontmatter, a description that says when to use the skill, SKILL.md
   under 500 lines, long checklists in `references/`, nothing
   agent-specific in SKILL.md.
2. Run the validator locally:

   ```bash
   pip install "git+https://github.com/agentskills/agentskills#subdirectory=skills-ref"
   skills-ref validate skills/<skill-name>
   ```

3. Try the skill on at least one real or synthetic case and describe the
   result in your pull request.
4. Use [Conventional Commits](https://www.conventionalcommits.org/) with a
   [gitmoji](https://gitmoji.dev/) after the type, such as
   `feat: ✨ add ...` or `fix: 🐛 ...`, for commit messages and the pull
   request title. See [AGENTS.md](AGENTS.md#commits) for the list.

## License

By contributing, you agree that your contributions are licensed under the
[MIT License](LICENSE).
