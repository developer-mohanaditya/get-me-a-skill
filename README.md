# Get Me a Skill

Find and assess agent skills for any job. The skill checks what the work actually requires, searches existing skills, inspects likely matches, and recommends whether to use, combine, adapt, or build. It treats [skills.sh](https://skills.sh/) as a discovery source, not a quality verdict. This project is independent of skills.sh and Vercel's `find-skills` skill.

## Use it

The portable skill is at [`skills/get-me-a-skill/SKILL.md`](skills/get-me-a-skill/SKILL.md). Agents that support the Agent Skills format can install it from this repository, for example:

```bash
npx skills add developer-mohanaditya/get-me-a-skill --skill get-me-a-skill
```

In Codex, invoke `$get-me-a-skill`. In ChatGPT, select `@get-me-a-skill` when the skill is available. Include the job, the required depth, and any constraints. The agent may ask a few focused questions if they would change the match.

This repository also includes a portable [`plugin.json`](plugin.json) for plugin hosts. The skill itself needs web or repository search access to discover external skills; it does not bundle credentials or a data connector. Available sources depend on the host agent's tools.

## Maintain it

Edit the skill in `skills/get-me-a-skill/`, validate its frontmatter and package, and try the prompts in [`evals/cases.md`](evals/cases.md) before releasing a new version. Update `plugin.json`'s version when publishing behavior changes. Keep examples and source-specific commands current as registries evolve.

## License

MIT. See [LICENSE](LICENSE).
