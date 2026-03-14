# Organize Generated Files

A Codex skill that keeps AI-generated files organized by workflow, artifact role, and file type instead of scattering them across the project root.

## What It Does

This skill tells the agent to decide file placement before writing files, keep the root directory clean, and group related outputs into a small and predictable folder structure.

It is designed for cases where AI produces scripts, reports, datasets, charts, drafts, logs, temporary exports, or other generated artifacts and needs to place them in sensible folders.

## Core Rules

- Group by workflow or task first.
- Use file type as a secondary rule.
- Separate source files, temporary files, intermediate outputs, and final deliverables.
- Create folders when a batch of related files would otherwise clutter the root.
- Reuse existing repository conventions when they are already clear.

## Suggested Folder Patterns

When a repository has no established structure, the skill favors patterns like:

- `src/`
- `scripts/`
- `data/raw/`
- `data/processed/`
- `outputs/`
- `outputs/reports/`
- `outputs/figures/`
- `logs/`
- `tmp/`
- `drafts/`
- `archive/`

## Files

- `SKILL.md`: skill instructions and placement heuristics
- `agents/openai.yaml`: UI-facing metadata for skill invocation

## Example Invocation

```text
Use $organize-generated-files to place new files into a clean, predictable folder structure.
```

## Typical Use Cases

- Prevent generated files from piling up in the project root
- Keep analysis scripts and their outputs separated
- Store charts, reports, logs, and temporary exports in consistent locations
- Enforce a cleaner structure for multi-step AI workflows

## Publishing

This folder can be published as a standalone GitHub repository or copied into a broader Codex skills collection.
