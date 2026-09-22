# Enrique Botía Barberá — portfolio

Source for my [personal website](https://ebotiab.github.io/), covering Python backend engineering, applied AI, projects and professional experience.

The website is available in Spanish and English. It is built with **MkDocs Material** and **mkdocs-static-i18n**, and published with GitHub Pages.

## Run locally

Requires **Python 3.11 or newer** and **uv**.

```bash
git clone https://github.com/ebotiab/ebotiab.github.io.git
cd ebotiab.github.io
uv sync
uv run mkdocs serve
```

Open the local address printed by MkDocs.

## Edit the content

| Path | Purpose |
| --- | --- |
| `docs/index.md` | Home page in Spanish. |
| `docs/about.md` | Background and education. |
| `docs/projects.md` | Projects and professional experience. |
| `docs/services.md` | Services. |
| `docs/contact.md` | Contact information. |
| `docs/*.en.md` | English counterparts of the pages above. |
| `docs/assets/` | Images and custom CSS. |
| `mkdocs.yml` | Navigation, theme and language configuration. |

Keep the Spanish page and its `.en.md` counterpart aligned when updating content. Spanish is the default language; the configured fallback displays default-language content when a translation is missing.

## Build and deployment

```bash
uv run mkdocs build
```

The generated site is written to `site/`. The [deployment workflow](.github/workflows/deploy.yml) builds and publishes the website on pushes to `main`; it can also be started manually from GitHub Actions.

See [pyproject.toml](pyproject.toml) for dependencies and `uv.lock` for the locked environment.
