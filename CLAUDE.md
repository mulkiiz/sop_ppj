# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this directory is

`sop ppj/` contains Word document templates for PPJ (Portal Pengelolaan Jurnal) administrative procedures. No runnable code lives here.

| File | Purpose |
|------|---------|
| `R1 SOP-Pembuatan-Jurnal-Baru.docx` | SOP for creating new journals in the system |
| `R1 Template-Surat-Usulan-Jurnal-Baru.docx` | Letter template for journal proposal |
| `R1 Template-Lampiran-Formulir-Usulan-Jurnal-Baru.docx` | Attachment form template for journal proposals |

## Related codebase

The application these SOPs describe is in `../simonju/` — a PHP/MySQL web app (SIMONJU) for journal management and OJS crawler automation. See `../simonju/AGENTS.md` and `../simonju/docs/README.md` for full technical context.

## Architecture (simonju summary)

- PHP 7.3, no Composer, no framework, procedural style
- `mysqli` prepared statements; CSRF on all POST forms; `htmlspecialchars()` for output escaping
- Two user roles: `admin/` (dashboard, crawler management) and `jurnal/` (journal-user view)
- `konfirmasi/` handles journal registration confirmation flow
- `includes/config.php` — central config (DB creds, secret keys, cron token, crawler settings)
- `cron/` — token-protected cron endpoints for automated OJS crawling
- Deployed as plain PHP files on cPanel (`jurnalsinta.id`); no build step

## Workspace

Both directories are part of `ppj_simonju.code-workspace` (VS Code multi-root workspace at `C:\xampp\htdocs\`).
