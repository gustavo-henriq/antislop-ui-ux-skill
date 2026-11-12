# Changelog

## 0.2.0 — unreleased

- The skill is now written in English and answers in the user's language.
- New layout: the skill lives in `skills/deslop/`; showcase material stays in `docs/`.
- `SKILL.md` cut from 422 to about 200 lines, with one description of the cycle and five question stops. The detail moved to `reference/` and is read at the step that needs it.
- Project data moved to `<project>/.deslop/` (`taste.md`, `recipes.md`, `profile.md`). Legacy `gosto.md` / `receitas.md` are still read.
- New `profile.md`: product language, output target, and the font, icon and illustration stance are asked on the first run instead of being fixed by the skill.
- Implementation can target the project's own code, not only an HTML prototype.
- Fallbacks for agents without a question tool, subagents, a browser or image generation.
- Reference search: search-scope question, candidate sheet, and the subagent collects while the main agent judges.
- `reference/copy.md`: AI copy tells listed per language (English and Brazilian Portuguese).
- Added a licence (MIT) and a structure for before/after cases in `docs/cases/`.

## 0.1.0 — 2026-11-06

- First public version, in Portuguese.
