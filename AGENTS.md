# Repository Guidelines

## Project Structure & Module Organization
This repository is a small static site with Jekyll support.

- `index.html`: main page template and markup.
- `src/`: authored assets (`style.css`, jQuery, Bootstrap CSS/JS/images).
- `_config.yml`: Jekyll configuration (currently minimal).
- `Gemfile`: Ruby dependencies (Jekyll).
- `_site/`: generated build output. Treat as derived artifacts; edit source files instead.

Keep new authored assets under `src/` and use relative paths from `index.html`.

## Build, Test, and Development Commands
Run commands from the repository root:

- `bundle install`: install Ruby gems from `Gemfile`.
- `bundle exec jekyll serve`: build and serve locally (default `http://127.0.0.1:4000`).
- `bundle exec jekyll build`: generate a production-style build into `_site/`.

Use `jekyll build` as the minimum pre-PR smoke check.

## Coding Style & Naming Conventions
- Follow existing file-local style when editing (HTML/CSS currently use tab-indented blocks).
- Use lowercase, descriptive filenames for new assets (example: `src/profile-links.css`).
- Prefer semantic HTML and keep CSS selectors straightforward (`#id`, `.class`, element selectors).
- Do not hand-edit minified third-party files unless intentionally upgrading vendored dependencies.
- Prefer `https://` URLs for any external assets.

## Testing Guidelines
There is no automated test suite in this repository today.

Before opening a PR:

1. Run `bundle exec jekyll build` and confirm it exits cleanly.
2. Run `bundle exec jekyll serve` and verify rendering in a browser.
3. Manually check updated links, layout, and asset loading (desktop + narrow/mobile width).

If you add JavaScript behavior, include reproducible manual test steps in the PR description.

## Commit & Pull Request Guidelines
- Write concise, imperative commit messages aligned with project history (examples: `Add profile links`, `Update README`).
- Keep commits focused to one logical change.
- PRs should include: change summary, verification steps/commands run, and screenshots for visual updates.
- Link related issues when available and call out any follow-up work explicitly.
