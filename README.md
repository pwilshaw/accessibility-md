# ACCESSIBILITY.md

A ready-made accessibility standard for your project. Drop one file into your repo, and your team and your AI coding agents all build to WCAG 2.2 AA.

It covers colour, text, layout, motion, images, audio and video, keyboard, touch, forms, semantics, ARIA and content, plus documents, emails, slides and social posts. It has rules written for AI agents too. Each rule is one plain line and names the WCAG criterion and level it comes from. The file ends with how to test and a Definition of Done checklist.

It's based on the [Accessibility for Humans](https://cards.designedforhumans.tech) cards by [Designed for Humans](https://designedforhumans.tech).

## Get it

Run this in the root of your project:

```sh
curl -O https://raw.githubusercontent.com/pwilshaw/accessibility-md/main/ACCESSIBILITY.md
```

Or [download ACCESSIBILITY.md](https://raw.githubusercontent.com/pwilshaw/accessibility-md/main/ACCESSIBILITY.md) and save it to your project root.

## Use it

### 1. Point your AI agents at it

Add this line to whichever instructions file your tools read:

```md
Follow ACCESSIBILITY.md for all UI, content and front-end work. Check the Definition of Done before you finish.
```

| Tool | File |
|---|---|
| Claude Code | `CLAUDE.md` |
| Codex, Jules and others | `AGENTS.md` |
| GitHub Copilot | `.github/copilot-instructions.md` |
| Cursor | `.cursor/rules/accessibility.mdc` |
| Windsurf | `.windsurfrules` |

### 2. Put the checklist in your pull requests

Copy the **Definition of Done** checklist into `.github/pull_request_template.md`, so every PR gets checked.

### 3. Make it yours

It's a starting point. Change the bar, cut what doesn't apply, add your own rules and link it from your contributing guide. If your product is public, publish an accessibility statement too. The file explains what goes in one.

## Stay up to date

WCAG and the law change. To see what's new, watch this repo or compare your copy with the latest:

```sh
curl -s https://raw.githubusercontent.com/pwilshaw/accessibility-md/main/ACCESSIBILITY.md | diff ACCESSIBILITY.md -
```

## Contribute

Spotted a mistake or a missing rule? Open an issue or a pull request. Please link a source for any facts or figures.

## Licence

[CC BY 4.0](LICENSE). Use it, change it and share it, including in commercial work. Just credit Designed for Humans and link back here.
