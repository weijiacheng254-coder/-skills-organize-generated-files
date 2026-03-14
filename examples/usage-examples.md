# Usage Examples

## Example 1: Analysis Workflow

Prompt:

```text
Use $organize-generated-files and create a data-cleaning script, a processed CSV, two figures, and a final markdown report.
```

Expected structure:

```text
project/
  scripts/
    clean_data.py
  data/
    processed/
      cleaned.csv
  outputs/
    figures/
      figure_1.png
      figure_2.png
    reports/
      summary.md
```

## Example 2: Scraper Workflow

Prompt:

```text
Use $organize-generated-files and generate a scraper, a sample input file, a run log, and an export CSV.
```

Expected structure:

```text
project/
  scripts/
    scraper.py
  data/
    raw/
      sample_input.json
  data/
    processed/
      export.csv
  logs/
    scraper.log
```

## Example 3: Document Drafting Workflow

Prompt:

```text
Use $organize-generated-files and draft three report sections, keep one final version, and store temporary notes separately.
```

Expected structure:

```text
project/
  drafts/
    section_1.md
    section_2.md
    section_3.md
    notes.md
  outputs/
    reports/
      final_report.md
```
