---
name: create-mindmaps
description: Convert documents, requirements, research, plans, meeting notes, or brainstorms into editable mind maps, Mermaid mindmap/flowchart source, hierarchical outlines, or ProcessOn-friendly structures. Use when the user asks for a mind map, knowledge map, concept map, tree, flowchart, or visual decomposition.
---

# 思维导图

## Choose the representation

- Concept hierarchy or knowledge summary: Mermaid `mindmap`.
- Ordered process, branches, decisions, or dependencies: Mermaid `flowchart`.
- ProcessOn import or broad compatibility: provide a clean tab-indented outline in addition to Mermaid.
- Large maps: split by domain rather than creating an unreadable single canvas.

## Workflow

1. Identify the root question and the 3-7 primary branches.
2. Normalize sibling levels to one taxonomy and remove duplicate concepts.
3. Keep labels concise while preserving dates, owners, metrics, or evidence that affect meaning.
4. Write the editable source to `.md` or `.mmd`.
5. If Mermaid CLI is available, render SVG/PNG and inspect syntax and legibility. Otherwise validate the source structure and say rendering was not performed.

Avoid placing secrets, personal data, or unsupported raw HTML in Mermaid labels. Escape punctuation when required by Mermaid syntax.
