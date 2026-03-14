---
name: organize-generated-files
description: Keep newly created files organized by workflow, artifact role, and file type instead of scattering them across the project root. Use when Codex is about to generate multiple files, derived outputs, reports, scripts, logs, drafts, datasets, charts, exports, or any new project artifacts and needs to decide where they should live, which folders to create, and how to keep related files grouped predictably.
---

# Organize Generated Files

## Overview

Plan file placement before writing files. Prefer a small, predictable folder tree that groups files by the work they belong to, then by artifact type when needed.

Keep the project root clean. Only place a file in the root when it is a true top-level control file such as `README.md`, `.env.example`, `package.json`, `requirements.txt`, `docker-compose.yml`, or a repo-wide entrypoint.

## Workflow

1. Inspect the existing project tree before creating new files.
2. Reuse established folders and naming patterns when the repository already has a clear convention.
3. Choose the folder based on generation logic first, file extension second.
4. Create a new folder when the output set belongs to a distinct workflow and would otherwise clutter an existing directory.
5. Keep source, intermediate, and final deliverables separate.
6. State the intended location in the response before or while creating substantial batches of files.

## Placement Rules

Apply these rules in order:

1. Group by workflow or feature.
   Place files that serve one task in a shared folder even when their extensions differ.
   Example: a scraper script, its config, a sample input, and a README note belong together.

2. Split by artifact role inside that workflow when volume increases.
   Use subfolders such as `src`, `data`, `outputs`, `figures`, `logs`, `tmp`, `drafts`, or `archive` only when they reduce clutter.

3. Use file type as a tiebreaker, not the primary rule.
   If no workflow grouping exists, then cluster by artifact family such as documents, tables, images, scripts, or logs.

4. Separate final deliverables from generated intermediates.
   Do not mix polished files with scratch files, temporary exports, checkpoints, or rerun outputs.

## Recommended Folder Meanings

Use these names when the repo has no better convention:

- `src/`: code meant to be maintained
- `scripts/`: runnable one-off or support automation
- `data/raw/`: untouched inputs
- `data/processed/`: cleaned or transformed datasets
- `outputs/`: final exported artifacts for users
- `outputs/reports/`: reports, writeups, summaries
- `outputs/figures/`: charts, diagrams, rendered images
- `logs/`: run logs and debug traces
- `tmp/`: disposable intermediates, checkpoints, test exports
- `drafts/`: editable working documents not yet final
- `archive/`: old outputs kept only for reference

## Naming Rules

Use names that reveal both purpose and lifecycle.

- Prefer descriptive names over generic ones like `result`, `new`, `test2`, or `final_final`.
- Add a workflow prefix when several tasks coexist in one project.
- Add version, date, or run identifiers only when they help distinguish repeated outputs.
- Keep temporary markers explicit: `_tmp`, `_draft`, `_scratch`, `_checkpoint`.
- Do not create many sibling files with near-identical names in the root.

## Folder Creation Heuristics

Create a folder instead of dropping files into the current directory when any of these is true:

- More than 2-3 related files will be generated.
- A task produces both code and artifacts.
- A workflow has raw, processed, and final stages.
- Outputs are likely to be rerun or regenerated.
- The filenames would otherwise need long prefixes just to stay understandable.

Avoid unnecessary nesting. Stop when the structure is clear and easy to scan.

## Decision Examples

- A new analysis script plus its CSV outputs:
  Put the script in `scripts/` or a workflow folder such as `steam-analysis/`, and put generated tables in `outputs/` or `data/processed/` depending on whether they are final or intermediate.
- A batch of charts for a report:
  Put them in `outputs/figures/` or a report-specific folder, not next to source scripts.
- Temporary compiler output, cached transforms, or debug dumps:
  Put them in `tmp/` or `logs/`, never beside final documents.
- Multiple drafts of a paper section:
  Put them in `drafts/` or a topic-specific draft folder, then move the accepted version to `outputs/reports/` or the repository's document area.

## Conflict Resolution

If the repository already uses a clear convention, follow it even if it differs from this skill.

If no convention exists and several placements seem plausible, prefer:

1. workflow grouping
2. separation by lifecycle stage
3. shallow, readable directories
4. consistent reuse of folder names

## Operating Rule

Before writing a substantial set of files, decide:

1. Which files are source, intermediate, and final
2. Which files belong to one workflow
3. Whether a new folder reduces root clutter

Then create the minimal folder structure needed and place every new file accordingly.
