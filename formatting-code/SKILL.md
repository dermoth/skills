---
name: formatting-code
description: "The user's code formatting and style standards per language, and how to handle code that deviates from them. Use before writing or editing code in any language or Markdown documents, and when deciding whether to reformat existing code."
---

# Formatting code

## Which standard applies

1. Documented project standard (style guide, CONTRIBUTING, linter/formatter
   config such as `.editorconfig`, `.clang-format`, `pyproject.toml`), or an
   obvious, consistent convention throughout the repo.
2. Otherwise the language standard documented under `reference/`.
3. Otherwise, **ask the user to define the style for that language**, then
   record the answer in `reference/<language>.md` (see `managing-skills`).

Do not infer standards from the user's past code; their style has changed
over time.

## Code that deviates from the standard

* Reformat first, as a separate commit, before making functional changes.
* If the repo is internally consistent but differs from the documented
  standard in `reference/`, ask the user whether it should be reformatted
  before doing so.

## General rule: tabs for indent, spaces for alignment

For most languages (C, Perl, shell, JavaScript, Go, ...) indent with tabs and
align with spaces, so code stays aligned regardless of tab width. Notable
exceptions: HTML/XML (and CSS/JSON) and Python use spaces. A language file
below overrides this rule.

## Language standards

One file per language under `reference/`; list each here.

* [JavaScript](reference/javascript.md)
* [HTML, XML, CSS, JSON](reference/html.md)
* [Markdown](reference/markdown.md)
