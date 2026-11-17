# DGM Marketing Skills

This repo has 5 agent skills for Claude Code and for other agents that read `SKILL.md` files. I made them from my notes in the TMU Digital Growth Marketing program, while I did SEO and marketing for Avateq.

Each skill is a folder with a `SKILL.md` file and, for most skills, a `references/` folder. The agent reads `SKILL.md` first and opens a reference file only when a step tells it to.

## Skills

| Skill | What it does | When to use it |
|---|---|---|
| [helpful-content](helpful-content/) | Writes or reviews a web page against Google's helpful content and E-E-A-T guidance, with results-page research, query types, FAQs, and technical basics. | You write, rewrite, or review a page, a blog post, or a product review for search and AI answer engines. |
| [conversion-page](conversion-page/) | Audits or writes a page that must convert: a homepage, a topic page, a landing page, or a product page. Gives a ranked list of fixes with evidence from the page. | A page does not convert, or you need landing page or product page copy. |
| [growth-experiment](growth-experiment/) | Turns a business question into a filled experiment brief: the decision, the hypothesis, the graded evidence, the method, the metrics, and the result. | You plan an A/B test, a false door, or customer interviews, or you read a test result. |
| [paid-social](paid-social/) | Plans or audits paid social ads on Meta, with notes for LinkedIn: signals, account ownership, structure, audiences, budget split, creative, and launch rules. | You plan a first Meta campaign, or you audit an ad account or an agency setup. |
| [ad-law-canada](ad-law-canada/) | Gives a risk review of marketing material for Canada: claims, prices and fees, CASL consent, contests, green and health claims, AI images, and privacy. It is not legal advice. | Material for Canadian customers must pass a legal risk check before it ships. |

The skills refer to each other. For example, `conversion-page` sends test ideas to `growth-experiment`, and `conversion-page`, `growth-experiment`, and `paid-social` send Canadian material to `ad-law-canada`. Install all 5 to get those links.

## Install

1. Copy a skill folder into `~/.claude/skills/` for all your projects, or into `.claude/skills/` of 1 project.
2. Keep the folder name. It must match the `name` field in `SKILL.md`.
3. Start a new agent session. The agent loads the skill when your request matches its description.

Example:

```sh
git clone https://github.com/georgebnov/dgm-marketing-skills.git
cp -R dgm-marketing-skills/conversion-page ~/.claude/skills/
```

## Sources

The skills come from my notes in the TMU Digital Growth Marketing program, and from public Google Search Central documents. They contain no course slides, handouts, or images. The `ad-law-canada` skill gives information, not legal advice. Send each high-risk item to a lawyer.

## License

See [LICENSE](LICENSE).
