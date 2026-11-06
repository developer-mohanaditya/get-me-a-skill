# Get Me a Skill

Find and assess agent skills for any job. The skill clarifies what the work requires, searches existing skills, inspects likely matches, and recommends whether to use, combine, adapt, or build. It treats [skills.sh](https://skills.sh/) as a discovery source, not a quality verdict. This project is independent of skills.sh and Vercel's `find-skills` skill.

The canonical workflow is the open-standard [`SKILL.md`](skills/get-me-a-skill/SKILL.md). The [`plugin.json`](plugin.json) and marketplace entry package that same skill for ChatGPT and Codex; they are not required by other agents. No hosted service, API key, or agent-specific script is bundled.

## Install across agents

Use a global installation when you want the skill in all projects. The [Skills CLI](https://skills.sh/docs/cli) accepts agent targets; select the agent you use instead of installing to every agent automatically.

| Host | Global installation or skill location | Invocation |
| --- | --- | --- |
| Claude Code | `npx skills add developer-mohanaditya/get-me-a-skill -g -a claude-code -s get-me-a-skill` | Select or invoke the skill by name. |
| Codex, OpenCode, Freebuff CLI, DeepSeek Harness, Deep Code | `npx skills add developer-mohanaditya/get-me-a-skill -g -a universal -s get-me-a-skill` installs in the shared `~/.agents/skills/` directory these hosts can read. | Codex: `$get-me-a-skill`; OpenCode: select the skill; Freebuff: `/skill:get-me-a-skill`; Deep Code: select from `/`. |
| Google Antigravity app | Copy `skills/get-me-a-skill/` to `~/.gemini/config/skills/get-me-a-skill/`. Project installation in `.agents/skills/` also works. | Select the skill in Antigravity. |
| Other Agent Skills-compatible hosts | Use `npx skills add developer-mohanaditya/get-me-a-skill -g -a <agent-id> -s get-me-a-skill`, or copy the skill folder to the host's documented skill directory. | Use the host's skill picker or explicit invocation syntax. |

DeepSeek is also a model provider. A model does not install skills by itself; the host running it must load Agent Skills. Deep Code and DeepSeek Harness have compatible skill directories. For an agent without native skill loading, provide the `SKILL.md` text as instructions for a single conversation; automatic discovery and reuse will not be available.

For the ChatGPT/Codex plugin package, add this repository as a marketplace and install the plugin:

```bash
codex plugin marketplace add developer-mohanaditya/get-me-a-skill --ref main
codex plugin add get-me-a-skill@get-me-a-skill
```

In ChatGPT, select `@get-me-a-skill` when the plugin is enabled. Include the job, required depth, and constraints. The skill may ask a few focused questions if they would change the match.

## Quality across hosts

The same instructions and hard gates apply everywhere. A full assessment requires current search, access to complete candidate skill files, and enough tools to verify claims or run a bounded trial. If a host lacks these capabilities, the skill must disclose the gap and produce a limited assessment. Installing the file cannot make different models or tools produce identical results.

Use [`evals/cases.md`](evals/cases.md) to compare hosts. Test both discovery and the final recommendation; seeing the skill in a menu proves installation only.

## Maintain it

Edit the canonical skill in `skills/get-me-a-skill/`, validate it against the [Agent Skills specification](https://agentskills.io/specification), and rerun the evaluation cases in each supported host before claiming parity. Bump `plugin.json`'s version for behavior changes. Users of the Skills CLI can run `npx skills update get-me-a-skill -g`; Codex plugin users can refresh the marketplace with `codex plugin marketplace upgrade get-me-a-skill` and update the installed plugin. Keep host paths current as agents change their discovery rules.

## License

MIT. See [LICENSE](LICENSE).
