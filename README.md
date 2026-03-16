# GitHub Badge Farming Skill

A [Claude Code](https://docs.anthropic.com/en/docs/claude-code) custom skill that provides step-by-step guidance for legitimately earning GitHub profile Achievement badges.

## What It Does

When you ask Claude Code about GitHub badges or achievements, this skill provides:

- Up-to-date (2026) methods that comply with GitHub ToS
- Step-by-step commands using GitHub CLI (`gh`)
- Badge tier requirements (Bronze / Silver / Gold / Platinum)
- Clear warnings about methods that no longer work or violate ToS

### Supported Badges

| Badge | Difficulty |
|---|---|
| Quickdraw | Easiest |
| YOLO | Easiest |
| Pull Shark | Easy |
| Pair Extraordinaire | Easy (needs 2nd account) |
| Public Sponsor | Easy ($1) |
| Galaxy Brain | Medium (needs others) |
| Starstruck | Hardest (needs community) |

## Installation

Add this skill to your Claude Code project:

```bash
claude mcp add-skill github-badge-farming -- https://github.com/easyvibecoding/Github-Badge-Farming-Skill
```

Or clone and add locally:

```bash
git clone https://github.com/easyvibecoding/Github-Badge-Farming-Skill.git
```

Then add to your `.claude/settings.json`:

```json
{
  "skills": [
    "/path/to/Github-Badge-Farming-Skill/SKILL.md"
  ]
}
```

## Usage

Just ask Claude Code naturally:

- "How do I get GitHub badges?"
- "Help me earn the Pull Shark badge"
- "What GitHub achievements can I get today?"
- "How do I get the Galaxy Brain badge?"

## Project Structure

```
.
├── SKILL.md              # Main skill definition & step-by-step guide
├── references/
│   └── badges.md         # Detailed badge rules & tier requirements
└── README.md
```

## License

MIT
