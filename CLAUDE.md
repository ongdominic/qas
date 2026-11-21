# QAS: work vault

Dom's vault for QAS, a company related to a Yi Hui shareholder but a separate business.
Dom manages QAS sales and growth. Private repo `ongdominic/qas`.
Same structure and rules as the `yihui` vault, separate data.
Timezone: Asia/Singapore (SGT, UTC+8). Currency: state SGD or USD every time.

## Who
`90 System/core/profile.md`.

## Structure
- `00 Inbox/` raw captures. No filing at capture time.
- `10 Projects/<kebab-slug>/` things with an end: `CLAUDE.md`, `_brief.md`, `_log.md`, `docs/`.
- `20 Areas/` ongoing: `Sales/` (pipeline, key accounts, pricing), `Growth/` (marketing, website, SEO).
- `30 Resources/` source material (catalogues, spec sheets), `40 Archive/` (nothing deleted), `90 System/`.

## Starting work
- Use `/resume <name>`. Read brief → last 5 log entries → only then specific files.
- Never read `40 Archive/_import-*/` (raw imports, old chats) unless Dom asks or a skill says so.
- Tasks live in Trello board "QAS To Do" (to be created). Mention overdue / due-today cards at start.

## Writing rules
- Never delete; move to `40 Archive/` with `git mv`. Never overwrite; add ` (2)` on clashes.
- Capture filenames `YYYY-MM-DD HHmm short-title.md`. No `\ / : * ? " < > | # ^ [ ]`.
- Log format:
  ```
  ## YYYY-MM-DD — <5-word summary>
  - Decided: ...
  - Learned: ...
  - Produced: [[...]]
  - Next: ...
  ```
- No secrets (passwords, API keys, Shopify tokens, bank details) in notes.

## Git rules
1. Before writing: `git pull --rebase --autostash`. On conflict, stop and tell Dom.
2. After writing: commit, then `git push origin HEAD:main`.
3. If push is rejected twice, push to `claude/*` and add `00 Inbox/CONFLICT <date>.md`.

## Boundaries
- QAS only. Yi Hui material lives in `yihui`; personal and Oddly in `brain`. Flag, don't file.
- The Shopify store and the `QAS website` code repo are QAS's; this vault holds notes and drafts.
- Never publish to Shopify or contact customers without Dom's go-ahead.
