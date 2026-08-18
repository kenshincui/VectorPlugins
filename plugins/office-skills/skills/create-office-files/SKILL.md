---
name: create-office-files
description: Create, read, edit, analyze, or convert local Microsoft Office-compatible files including DOCX, XLSX, CSV, and related formats. Use when the user asks for a Word document, spreadsheet, office report, file conversion, or edits to an existing office file.
---

# Office 文件

Produce real files, not Markdown renamed with an Office extension.

## Choose the toolchain

1. Inspect available runtimes and libraries before writing: Python 3, Node.js, `soffice`/LibreOffice, and relevant packages such as `python-docx`, `openpyxl`, `xlsxwriter`, or `pandas`.
2. Prefer a structured library for creation and edits. Use LibreOffice for conversion and render checks when available.
3. If a required dependency is missing, either install it only when the user authorized dependency changes or report the exact missing prerequisite.

## Workflow

1. Inspect source files and preserve unrelated content, formulas, styles, comments, and worksheet names.
2. Create or edit the requested artifact at an explicit path.
3. Reopen the output with an independent reader or library and verify key fields, sheet counts, formulas, row counts, headings, and file type.
4. When layout matters, render or convert to PDF and visually inspect representative pages.
5. Report the final file path, format, and validation performed.

## Guardrails

- Do not overwrite the only copy of an input file unless explicitly requested.
- Do not evaluate spreadsheet formulas or macros from untrusted files with a desktop Office application.
- Keep credentials and private source data out of generated examples and logs.
- For PowerPoint-specific work, prefer the dedicated `create-presentations` skill.
