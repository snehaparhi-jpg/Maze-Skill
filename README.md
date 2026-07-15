# maze-test

A Claude Code skill that generates complete, copy-paste-ready [Maze](https://maze.co) unmoderated usability test scripts for B2B back office product designs.

Built for the **Customer Product Line (CPL)** at Delivery Hero — covering the Pricing, Choice, and Seamless domains. Works with Figma prototypes (via MCP or link) and Claude-built prototypes living inside a Claude Code project.

---

## What it does

Invoke `/maze-test` inside Claude Code and the skill walks you through:

1. Selecting your domain (Pricing, Choice, or Seamless) and test focus (comprehension, workflows, confidence, A/B, gap finding)
2. Providing a PRD or initiative brief — paste it or pull from conversation context
3. Specifying your prototype source — Figma (with or without MCP), a Claude prototype in the current project, or TBD
4. Reviewing scope, estimating test time, and trimming if over 10 minutes
5. Receiving a full, formatted script: welcome message, scenario-based task missions, post-task questions with effort ratings and image hints, and a thank-you

After the script is delivered, the skill offers to draft a Slack or email outreach message to share the Maze test link with participants.

---

## Installation

### Global (available in all Claude Code sessions)

```bash
# Clone the repo
git clone git@github.com:snehaparhi-jpg/Maze-Skill.git

# Copy the skill file to your global commands directory
cp Maze-Skill/commands/maze-test.md ~/.claude/commands/maze-test.md
```

### Project-level (available only in a specific project)

```bash
# From your project root
mkdir -p .claude/commands
cp path/to/Maze-Skill/commands/maze-test.md .claude/commands/maze-test.md
```

Claude Code picks up skills from both `~/.claude/commands/` (global) and `.claude/commands/` (project-level) automatically — no restart needed.

---

## Usage

Open Claude Code in any session (or inside your prototype project) and run:

```
/maze-test
```

The skill guides you through the rest interactively.

**Tip for Claude prototype users:** If your prototype is a Claude-built app, trigger `/maze-test` from inside the project directory. The skill will scan the working directory for screen and route files and read them directly — no Figma link needed.

---

## Prototype sources supported

| Source | What happens |
|--------|-------------|
| **Figma + MCP connected** | Paste a Figma URL — skill pulls frame structure and page metadata via Figma MCP |
| **Figma link only** | Paste a Figma URL — used as a plain reference link, no frame content read |
| **Claude prototype (in project)** | No URL needed — skill scans the working directory for screen/route files and reads them directly |
| **No prototype yet** | All prototype fields output as TBD |

---

## Domain context

| Domain | Status |
|--------|--------|
| **Pricing** | Fully configured — Dynamic Pricing Service (DPS) |
| **Choice** | Fully configured — logistics optimization (delivery areas, supply/demand, vendor coverage) |
| **Seamless** | Needs setup — edit the Seamless row in `commands/maze-test.md` before use |

**Seamless designers:** before running the skill, open `commands/maze-test.md` and fill in the `[To be defined]` row in the Domain Context table with your product name, user personas, and scenario framing. The script quality depends on it.

---

## Requirements

- [Claude Code](https://claude.ai/code) CLI
- A Maze account (for running the test once the script is generated)
- Figma MCP (optional — only needed for the Figma + MCP prototype source option)

---

## Author

Sneha Parhi — Product Design, Customer Product Line, Delivery Hero
