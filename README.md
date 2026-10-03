# 🎮 Level Lifeline

**Stuck on a level, boss or team build? Get the best guide and the top community tip in one short reply.**

![Agent Skill](https://img.shields.io/badge/Agent_Skill-SKILL.md-6C47FF?style=flat-square)
![Built for](https://img.shields.io/badge/Built_for-BlueAI_Skillathon_2026-0A84FF?style=flat-square)

Level Lifeline is an agent skill (a `SKILL.md` plus three reference files). Describe what you're stuck on in plain language. It opens Chrome, searches for a walkthrough, reads the Google AI Overview if one appears, opens the best guide and scrolls to the strategy, then looks up the top community post on Reddit. You get the site, the link, a 3-line summary and the Reddit post, with no alt-tabbing. It was first named Quest Guide.

<!-- TODO: add a screenshot or GIF of the skill in action here -->
<!-- TODO: add a link to the demo video here -->

---

## Try it

No special syntax. Just say what's wrong:

> I am stuck on Town Hall 12 in Clash of Clans
>
> How do I beat the Raiden Shogun boss in Genshin Impact?
>
> Help me unlock Bruno in Brawl Stars

It also triggers on phrases like "best strategy for", "I keep losing", "help me with this level", "how to unlock", "best team for" and "guide for". If the game or the problem is missing, it asks one question before searching.

## What you get back

```
🎮 Quest Guide: [Problem] in [Game Name]

🌐 Web Guide
Website: [Site name]
Link: [Full URL]
Summary: exactly 3 lines
  1. The challenge and the recommended approach
  2. The key steps or items needed
  3. One important tip or warning

💬 Reddit
Post: [Exact post title]
Link: [Full Reddit post URL]
```

If a Reddit post won't load, you get the title only, never a made-up link.

## How it works

| Phase | Steps |
|---|---|
| **Web search** | 1. Confirm the game and the problem. 2-3. Open Chrome and a fresh tab. 4. Search `[game] [problem] walkthrough guide`. 5. Read the Google AI Overview if present. 6. Open the best trusted guide (game wikis first, then sites like Gamepur, IGN, GamesRadar, Pocket Tactics). 7. Scroll to the walkthrough or strategy section and note the site and URL. |
| **Reddit** | 8. Open Reddit. 9. Search `[game] [problem]`, sorted by Top or Hot. 10. Pick the most upvoted post that has real answers, preferring the game's own subreddit. |
| **Output** | 11. Combine both into the template in `references/output-template.md`. |

Strict rules: follow the steps in order, never invent a URL, never recommend cheats or anything against a game's terms of service, and say so honestly if both sources fail.

## Requirements

This skill drives a Chrome browser **inside BlueStacks**, so it is written for agents that can do that, such as BlueAI. To use it with another agent, edit Steps 2 and 8 in `SKILL.md` to point at your own browser tool.

It needs no API keys, accounts or logins.

## Install

**Claude Code and compatible agents.** Clone the repo straight into your skills folder:

```bash
git clone https://github.com/Umang1617/level-lifeline.git ~/.claude/skills/level-lifeline
```

**Other agents.** Copy `SKILL.md` and the `references/` folder into a folder named `level-lifeline` inside wherever your agent loads skills from, or upload the packaged skill file where skill uploads are supported.

## Make it yours

| To change | Edit |
|---|---|
| Subreddits per game, how Reddit posts are picked, quality signals | `references/reddit-sources.md` |
| Layout and wording of the final answer | `references/output-template.md` |
| Steps, rules, edge cases and trigger phrases | `SKILL.md` |
| Background notes on trusted guide sites (not loaded automatically) | `references/web-sources.md` |

## Repo contents

```
level-lifeline/
├── SKILL.md                      # the skill: trigger, 11 steps, rules, edge cases
├── references/
│   ├── reddit-sources.md         # subreddits per game and post-quality signals
│   ├── output-template.md        # the exact response format
│   └── web-sources.md            # notes on trusted guide sites
├── README.md
├── LICENSE
└── .gitignore
```

## Good to know

- **Guides go stale.** Games get patched. Check that a guide matches your current version before following it.
- **The AI Overview doesn't always appear.** When it doesn't, the skill skips that step and relies on the guide itself.
- **Web and Reddit content is untrusted.** Posts and pages are read as-is, so use your judgment before acting on them.
- **Never share personal details or log in through the agent.** Level Lifeline only needs a game name and a problem.
- **Third-party names.** Game, website and platform names in this project belong to their owners. This project is not affiliated with or endorsed by any of them. Check each site's terms of use before using this skill at scale.

## Roadmap

- [ ] Add more games and subreddits to the lookup table
- [ ] A mode for agents without BlueStacks
- [ ] Optional video guide link

## Credits

Built by [Umang Srivastava](https://www.linkedin.com/in/umang1617/) for the BlueAI Skillathon 2026.

