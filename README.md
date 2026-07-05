# Portfolio CMS Manager

A Windows desktop content-management app for maintaining a static HTML portfolio without manually editing project card markup every time a new project is added.

The app lets you fill in project metadata, choose a cover image, write case-study sections, and generate both a Notion-style gallery card and a full project page.

## Features

- Select a local portfolio repo folder
- Add project title, slug, category, status, description, GitHub link, and tech stack
- Pick a cover image and copy it into `assets/covers/`
- Write case-study sections in a simple text format
- Generate `projects/<slug>/index.html`
- Insert or replace the matching project card in `index.html`
- Build into a Windows `.exe` with PyInstaller

## Why this exists

Static portfolios are fast and easy to host, but updating them manually can become repetitive and fragile. This tool adds a lightweight local CMS layer around a static portfolio so new projects can be added through a desktop interface instead of hand-editing HTML.

## Install for development

```bash
python -m venv .venv
.venv\Scripts\activate
pip install -r requirements.txt
python portfolio_manager_app.py
```

## Build the EXE

On Windows, double-click:

```txt
build_exe.bat
```

The output will be created at:

```txt
dist/Topium Portfolio Manager.exe
```

## How to use

1. Open the app.
2. Select the local portfolio repo folder.
3. Fill in project details.
4. Pick a cover image.
5. Write case-study sections.
6. Click **Generate Project**.
7. Review the changed files locally.
8. Commit and push the portfolio changes.

## Section format

The case-study editor uses headings ending with a colon.

```txt
Problem:
Adding projects manually is slow.

Build:
- Select portfolio folder.
- Fill metadata.
- Generate the card and page.

What it shows:
This shows static site automation and practical internal tooling.
```

## Generated output

For a project with slug `ai-study-assistant`, the app creates or updates:

```txt
assets/covers/ai-study-assistant-cover.png
projects/ai-study-assistant/index.html
index.html
```

## Tech stack

- Python
- customtkinter
- PyInstaller
- HTML generation
- static site automation
- filesystem tooling

## Status

Prototype. The first version focuses on generating new project cards and pages reliably. Future versions can add live preview, editing existing projects, drag-and-drop images, and a Git commit button.
