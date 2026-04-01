# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository Purpose

This is a personal workspace-settings repository storing configuration and tooling for VSCode, shell environments, and AI coding agents.

## Structure Overview

- **`VSCode/`** — VSCode configuration: profiles, snippets, custom CSS/JS, and theme screenshots
- **`.agents/skills/`** — Reusable AI agent skills installable via `npx skills add ...`
- **`.gitignore-templates/`** — Gitignore templates for Python, Go, Node/TS, Terraform

## Claude Code Configuration (`.claude/`)

- **`settings.local.json`** — grants `WebFetch` permission to `skills.sh`, required when installing or browsing skills from that domain
- **`README.md`** — reference for the exact `npx skills add` commands used to install each skill in this repo

## Skills System

Skills live in `.agents/skills/<skill-name>/` and each contains a `SKILL.md` with frontmatter (`name`, `description`) and instructions for the AI.

To install a skill from an external source:
```sh
npx skills add <github-url> --skill <skill-name>
```

Current skills:
- **`systematic-debugging`** — 4-phase debugging process (root cause → pattern → hypothesis → fix). Use before proposing any fix.
- **`brainstorming`** — Spec document review and visual companion prompts
- **`vercel-react-best-practices`** — Performance rules for React/Next.js/Vercel apps
- **`interface-design`** — UI critique, principles, and validation references
- **`changelog-generator`** — Transforms git commits into user-facing release notes

## Debugging Approach

When encountering any bug or unexpected behavior, the `systematic-debugging` skill mandates:
1. Find root cause **before** proposing any fix
2. Never attempt more than 3 fixes without questioning the architecture
3. Add diagnostic instrumentation at component boundaries before hypothesizing

This is not optional — proposing fixes without root cause investigation violates the process.
