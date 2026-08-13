# Diehleon.github.io

Personal portfolio built with Jekyll and hosted on GitHub Pages.

---

## 1. Get it online

Copy every file in this folder into the root of your `Diehleon.github.io` repo, then:

```bash
git add .
git commit -m "Add portfolio site"
git push origin main
```

Then in your repo on github.com: **Settings → Pages → Build and deployment**
Set **Source** to `Deploy from a branch`, **Branch** to `main` and folder to `/ (root)`, and Save.

Give it about a minute, then open **https://Diehleon.github.io**. The **Actions** tab
shows the build — a green check means it deployed, a red X means something in a
Markdown file's front matter is malformed.

> Do **not** add a `.nojekyll` file. That switch turns Jekyll off entirely and you'd
> get raw Markdown in the browser.

## 2. Make it yours

Open `_config.yml` and edit the top block — name, tagline, email, location, and your
social handles. That one file feeds the nav, footer, contact page and hero. Leave any
social field as `""` and its link disappears everywhere automatically.

**Any change to `_config.yml` requires restarting the local server** to take effect.
Changes to every other file are picked up live.

## 3. Add a project

Create a new file in `_projects/`, named after the URL you want
(`_projects/cnc-controller.md` becomes `/projects/cnc-controller/`):

```markdown
---
title: "CNC Motion Controller"
designator: "PRJ-002"
date: 2026-06-01
status: "In progress"
summary: "One or two sentences shown on the card."
tags: ["STM32", "C++", "Step/Dir"]
mcu: "STM32F411"
toolchain: "Arduino IDE"
repo: "https://github.com/Diehleon/cnc-controller"
cover: /assets/img/cnc.jpg
---

Your write-up in Markdown goes here.
```

Boards work identically — put them in `_pcb/` instead and use the hardware fields
(`layers`, `dimensions`, `eda`, `gerbers`). Every field is optional; anything you omit
is simply left off the page.

### Extra fields you can use

| Field | Effect |
| --- | --- |
| `cover` | Image at the top of the card and the detail page |
| `status` | Badge on the card — `Shipped`, `In progress`, `Fabricated` |
| `specs` | List of `label` / `value` pairs added to the spec sidebar |
| `gallery` | List of `src` / `caption` pairs rendered as an image grid |
| `demo` | Adds a "Live demo" button |

Images go in `assets/img/` and are referenced as `/assets/img/filename.jpg`.

## 4. Preview locally (optional)

You can skip this entirely and just push — GitHub rebuilds in about a minute. But if
you're changing CSS, a local server makes it instant.

**Windows** — install Ruby+Devkit from [rubyinstaller.org](https://rubyinstaller.org)
(pick the recommended version), then in a new terminal:

```bash
gem install bundler
cd path/to/Diehleon.github.io
bundle install
bundle exec jekyll serve --livereload
```

**macOS / Linux** — Ruby is already there; run the same three commands (macOS may need
`brew install ruby` first if the system Ruby complains).

Open **http://localhost:4000**. Edits to pages, layouts and CSS refresh on save.

## 5. Layout of this repo

```
_config.yml        Site settings — edit this first
index.html         Homepage
projects.html      Auto-generated list of everything in _projects/
pcb.html           Auto-generated list of everything in _pcb/
about.md           About page
resume.md          Resume page
contact.html       Contact page
_projects/         One Markdown file per project
_pcb/              One Markdown file per board
_layouts/          Page shells
_includes/         Nav, footer, card component
assets/css/        Stylesheet — the palette lives at the top
assets/img/        Photos
assets/files/      Resume PDF
```

## 6. Custom domain (later)

If you buy a domain, add a file named `CNAME` at the repo root containing just
`yourdomain.com`, then point an ALIAS/A record at GitHub's Pages IPs. Settings → Pages
walks you through the DNS side.
