# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an **Obsidian vault** for the book "세컨드 브레인은 옵시디언" (Second Brain with Obsidian). It serves as both a companion vault for readers and a working example of PARA + Zettelkasten note-taking methodologies.

## Vault Structure (PARA Method)

- `0. Slip-box/` — Zettelkasten permanent notes (영구 보관 노트). Notes tagged `#StructureNote` serve as structural index notes.
- `1. Projects/` — Active project notes (현재는 책 챕터별 내용)
- `1. Indexes.md` — Top-level index note with embedded Base views
- `2. Area/` — Ongoing area-of-responsibility notes
- `3. Resource/` — References, templates, and periodic notes
  - `references/` — Zettelkasten reference notes (참고 노트)
  - `templates/` — Templater templates (독서 노트, 일간/주간 노트, 공통 태그 노트)
  - `periodic notes/daily/` — Daily notes
- `4. Archive/` — Archived notes and attachments
- `Books/` — Book notes (for Dataview practice, per Ch 20)

## Key Plugins

Calendar, Dataview, Excalidraw, Periodic Notes, Templater, kr-book-info-plugin, Style Settings

## File Conventions

- Notes use **Obsidian Flavored Markdown** with wikilinks (`[[note]]`), callouts, and frontmatter properties
- Templates are in `3. Resource/templates/` (configured in `.obsidian/templates.json`)
- Templates use **Templater** syntax: `<% tp.file.creation_date() %>`, `<%* ... %>` for JS blocks
- `.base` files are Obsidian Bases (YAML-based database views with filters, formulas, and sort options)
- The vault language is **Korean**; note titles and content are in Korean
- CSS snippets in `.obsidian/snippets/`: `heading.css`, `numbered-headers.css`, `property-hover.css`

## 노트 검색 우선순위

노트를 찾을 때는 **QMD(MCP) 검색을 우선 사용**한다.

1. `search` — 키워드/정확한 문구 매칭 (~30ms, 가장 빠름)
2. `vector_search` — 의미 기반 검색, 다른 단어로 표현된 관련 개념도 찾음 (~2s)
3. `deep_search` — 쿼리를 자동 확장하여 키워드+의미 검색 후 재랭킹 (~10s)

QMD로 충분히 찾지 못할 때만 Glob/Grep 또는 Obsidian CLI를 사용한다.

## Working with This Vault

- When editing `.md` files, preserve Obsidian-specific syntax: `[[wikilinks]]`, `![[embeds]]`, callouts (`> [!NOTE]`), frontmatter YAML, Templater blocks (`<% %>` / `<%* %>`)
- When editing `.base` files, follow the YAML schema for filters, views, formulas, and sort
- Image references use Obsidian's format: `![|width](relative/path.png)`
- `.gitignore` only excludes `.DS_Store` files; `.obsidian/` config is tracked
- Block references use `^block-id` syntax at end of paragraphs, linked via `[[note#^block-id]]`
- Aliases are defined in frontmatter: `aliases: [제텔카스텐]`
