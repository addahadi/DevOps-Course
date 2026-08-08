# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## What this repository is

This is **not a software project** — it is an educational content project that produces a
university-quality DevOps course. There is no build system, no package manager, no tests, and no
runtime. The deliverables are standalone HTML documents that a learner opens directly in a browser.

`course/index.html` (the roadmap) is the **authoritative source of truth**. It defines the module
and lesson breakdown, the ordering, the milestones, the shared design system, and the intended shape
of the course. Re-read it before generating or revising any course material, and keep it consistent
with the lessons it links to.

The audience and teaching approach: a backend software engineer learning DevOps to ship their own
apps, *not* to become a DevOps engineer. Teach from first principles, always define terms before
using them, and favor depth over speed.

## Repository layout

```
course/index.html                                      # the roadmap (source of truth): 14 modules, lesson checklist, milestones
course/modules/NN-<slug>/lesson-NN-<slug>.html         # one file per lesson
```

Module folders and lesson files are numbered and slugged, e.g.
`course/modules/01-foundations/lesson-01-why-devops-exists.html`. The roadmap links to lessons by
this relative path, and the roadmap's lesson checklist tags each lesson with a `data-id` like `1.1`
(module.lesson). Keep folder names, file names, roadmap links, and `data-id`s in sync when adding
lessons.

## The course plan (from the roadmap)

14 modules, ~95 lessons, ordered so each builds on the last: 1 Foundations · 2 Infrastructure & OS ·
3 Linux · 4 Networking · 5 Nginx & Proxies · 6 Virtualization & Cloud · 7 Docker · 8 Docker Compose ·
9 CI · 10 CD/Deployment · 11 Reliability & Security · 12 Observability · 13 Kubernetes (conceptual) ·
14 Production Architecture Capstone. The course progressively builds **one** production project
(React, Express, PostgreSQL, Redis, Docker Compose, GitHub Actions, Nginx, HTTPS, monitoring); every
new lesson should advance that same project rather than introduce a throwaway example.

## Hard output requirements (non-negotiable)

Every HTML deliverable must:
- Be **fully self-contained and work offline** — all CSS and JavaScript embedded inline, **no CDNs
  or external assets** of any kind (no web fonts, no remote images, no scripts).
- Define colors via **CSS variables** (design tokens), never hardcoded.
- Put the lesson/module title in the browser tab (`<title>`).
- Include "Previous Lesson" / "Next Lesson" navigation at the bottom.
- Use ASCII diagrams where a diagram helps.

When the roadmap or a lesson changes, **regenerate the entire corresponding HTML file** rather than
patching a fragment, so the document stays internally consistent.

## Shared design system

`course/index.html` and every lesson share the same design-token block — do not diverge from it.
Copy the `:root` token set (fonts, `--bg`/`--surface`/`--border`, semantic accent colors with `-soft`
variants, `--radius`, `--shadow`, `--maxw`) into each new lesson so all pages look like one course.

Theming: dark is the default. Light theme is supported two ways that must both be present —
`@media (prefers-color-scheme: light)` (respecting the OS) and an explicit `:root[data-theme="light"]`
/ `[data-theme="dark"]` override set by an in-page toggle button. The toggle persists the choice in
`localStorage`; the roadmap also persists lesson-completion checkboxes in `localStorage`. All
`localStorage` access is wrapped in try/catch so the pages work when storage is unavailable.

## Required lesson structure

Each lesson must contain these 16 sections in order: Problem Statement · Historical
Context · Previous Solution · Why It Failed · New Solution · Internal Mechanics · Real Industry
Example · Diagrams · Advantages · Limitations · Common Misconceptions · Practical Use Cases · Summary
· Recommended Resources (official docs, best videos/books/articles, labs, repos) · Exercise · Quiz.

## Working in this repo

To preview a page, open the `.html` file directly in a browser (e.g.
`start course/index.html` on Windows) — there is nothing to build or serve.
