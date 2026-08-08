# DevOps Course — from first principles

A university-quality, **build-in-public** DevOps course for backend engineers who want to learn how
to actually ship and operate their own apps — not to become a DevOps engineer, but to understand
every box between `git push` and production and be able to defend each one.

I'm writing this course **while I learn it myself**, and publishing it here so others can follow
along. Everything is free, offline-friendly, and open in your browser — no build step, no accounts,
no tracking.

> **Status:** in active development. Lessons are added module by module. Some lessons are live today;
> the rest are marked _soon_ on the roadmap.

## Start here

Open **[`course/index.html`](course/index.html)** in your browser — that's the roadmap and the
source of truth. It links every lesson, tracks your progress (checkboxes saved in your browser), and
lets you toggle light/dark theme.

```bash
# macOS
open course/index.html
# Linux
xdg-open course/index.html
# Windows (PowerShell)
start course/index.html
```

Or just double-click the file. There is nothing to install.

## What makes this course different

- **First principles, always.** Every term is defined before it's used. We favor depth over speed.
- **One project, the whole way through.** You build and operate **DevBoard**, a collaborative task
  board (a minimal Trello), from an empty repo to a monitored, HTTPS, zero-downtime production
  deployment. Every lesson advances the *same* app instead of tossing out throwaway examples.
- **Real production, not localhost.** From Module 2 on you use a small real server (~$5/month) and a
  domain (~$10/year) — the one non-negotiable cost, because you can't learn production on localhost.
- **Self-contained HTML.** Each lesson is a single offline HTML file with embedded CSS/JS — no CDNs,
  no external assets. Read on a plane, fork it, host it anywhere.

## The DevBoard stack (fixed for the whole course)

React · Express (Node.js) · PostgreSQL · Redis · Docker + Compose · GitHub Actions · Nginx ·
Prometheus / Grafana / Loki.

## The 14 modules

| # | Module | Focus |
|---|--------|-------|
| 1 | Foundations & Why DevOps Exists | The whole map: what happens between `git push` and production |
| 2 | Machines: Infrastructure & Operating Systems | Servers, kernels, processes, memory, storage |
| 3 | Linux Fundamentals for Engineers | Filesystem, permissions, shell, systemd, SSH, triage |
| 4 | Networking from First Principles | TCP/IP, routing, DNS, HTTP/1–3, TLS & HTTPS |
| 5 | Serving Traffic | Web servers, reverse proxies, Nginx, load balancing |
| 6 | Virtualization & Cloud Computing | Hypervisors, VMs, regions/AZs, IaaS→FaaS, cost |
| 7 | Containers & Docker | Namespaces, cgroups, images, Dockerfiles, networking, volumes |
| 8 | Composing a System | Docker Compose, Twelve-Factor config & secrets |
| 9 | Continuous Integration | CI gates on every pull request |
| 10 | Continuous Delivery & Deployment | Push to main → zero-downtime deploy |
| 11 | Production Reality | Reliability & security: backups, secrets, restore drills |
| 12 | Monitoring, Logging & Observability | Metrics, dashboards, alerts, structured logs |
| 13 | Orchestration | Kubernetes, conceptually |
| 14 | Production Architecture | Capstone: design & defend the end-state |

Roughly **95 lessons**. Each lesson follows the same structure: problem statement, historical
context, why the previous solution failed, the new solution and its internal mechanics, a real
industry example, diagrams, advantages, limitations, common misconceptions, practical use cases, a
summary, recommended resources, an exercise, and a quiz.

## Repository layout

```
course/index.html                                    # the roadmap (source of truth)
course/modules/NN-<slug>/lesson-NN-<slug>.html       # one self-contained file per lesson
```

## Contributing & feedback

This is a learning journey in the open. If you spot an error, a confusing explanation, or a gap,
please **open an issue** — corrections from people further along than me are especially welcome.

## License

Educational content, free to read and share. If you'd like a specific open license added
(e.g. CC BY 4.0), open an issue and I'll add it.
