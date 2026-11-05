# AGENTS.md

This file provides guidance to agents when working with code in this repository.

- The published site lives directly under [docs](docs/index.html); this is not a documentation-only directory. There is no package manifest, build pipeline, lint configuration, or automated test runner; no single-test command exists.
- For local preview from the repository root, run `python.exe -m http.server 8000 --directory docs`; visit the homepage, `/404.html`, and `/rod-coin.html` separately. This is a preview command, not an automated test.
- Keep the two template stacks separate: [homepage](docs/index.html:1672) and [error page](docs/404.html:269) use Bootstrap 5.0.0, while [ROD page](docs/rod-coin.html:674) uses local Bootstrap 3.3.7 and separate assets.
- Preserve script order: jQuery and plugins precede [main.js](docs/js/main.js:1); plugin initialization is unconditional, so one missing dependency can prevent later initialization.
- [paralax.js](docs/js/paralax.js:2) requires all three background layers and runs continuously; loading it on a page without those elements causes errors.
- [Bootstrap theme variables](docs/scss/bootstrap.scss:3) are not compiled automatically. Pages load [committed Bootstrap CSS](docs/css/bootstrap.min.css), then [custom CSS](docs/css/style.css); editing SCSS alone does not change served styling.
- No configuration establishes formatting, imports, types, naming, or error-handling conventions. Do not invent a repository-wide style contract from mixed legacy scripts.
- Template attribution is a license requirement in [LICENSE.txt](docs/LICENSE.txt:5); the ROD script also [injects attribution](docs/js-rod/script.js:37), so do not mistake it for removable dead code.
- [CNAME](docs/CNAME) records the custom domain; retain it when changing site assets.

## Local mode guidance
- [Coding](.spexcode/rules-code/AGENTS.md), [debugging](.spexcode/rules-debug/AGENTS.md), [questions](.spexcode/rules-ask/AGENTS.md), and [architecture](.spexcode/rules-architect/AGENTS.md) contain scoped discoveries. These files are local-only because the SpeXcode directory is ignored.
