---
name: manage-feishu
description: Use lark-cli to read, create, edit, search, or organize Feishu/Lark documents, Drive files, Wiki pages, Base tables, Sheets, calendars, messages, approvals, tasks, contacts, and meeting content. Use when a user provides a Feishu URL/token or explicitly asks to work with Feishu content or services.
---

# 飞书操作

Use `lark-cli` as the execution layer. Do not invent API responses or replace a missing CLI with browser automation unless the user explicitly requests that fallback.

## Workflow

1. Run `command -v lark-cli` and `lark-cli --version` before the first operation.
2. If unavailable, stop and explain that the plugin requires `lark-cli`; do not claim the plugin installed the CLI.
3. Inspect the relevant command help, for example `lark-cli docs --help`, before using an unfamiliar resource.
4. Prefer `--as user` so operations use the signed-in user's identity.
5. Read the smallest necessary scope first. For large documents, fetch an outline or targeted section rather than blindly loading everything.
6. Treat reading and writing as separate authority. A request to summarize, inspect, or recommend does not authorize edits, sends, approvals, or table mutations.
7. For a requested mutation, apply the narrowest change and read it back. For messages, approvals, or other external effects, return the tool receipt or ID.

## Routing

- Document or Wiki URL: route by `/docx/` or `/wiki/` path and token, not by hostname alone.
- Drive file operations: use `lark-cli drive` rather than rebuilding a document from extracted text.
- Sheets and Base: inspect schema and identifiers before changing cells or records.
- Calendar and messages: resolve the intended account, chat, user, or calendar before sending or creating anything.
- Authentication errors: report the missing identity/scope and let the user complete authentication; never ask for tokens in chat or commit credentials to files.

## Safety

- Never log or persist access tokens, cookies, app secrets, or authorization headers.
- Preserve embedded images, attachments, citations, sheets, Base references, comments, and unsupported blocks during document edits.
- Paginate until the API reports no more results when completeness matters.
- State whether the result is verified, partial, or blocked.
