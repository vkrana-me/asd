# ASD

ASD is a local-first learning product for intermediate developers preparing for system-design interviews. It turns one public JavaScript or TypeScript repository into a **Repository-Based Course** grounded in the repository's actual code.

> **Status:** Architecture and product design are complete. Application implementation has not started.

## What Learners Will Do

1. Choose a public GitHub repository and a branch, tag, or commit.
2. Create an immutable **Course Snapshot** through static analysis only; the product never installs dependencies or runs repository code.
3. Learn the repository's **High-Level Design (HLD)** before studying **Low-Level Design (LLD)** for core components and one Learner-selected **Deep Dive**.
4. Follow Repository Evidence links, complete active-recall checks, and finish with an Interview Walkthrough.
5. Use an opt-in, evidence-citing **Tutor** for repository-grounded questions.

## Local-First by Design

Course Snapshots, generated material, progress, Personal Notes, and Lesson Versions stay on the Learner's device and remain readable offline after generation. A Learner may configure an OpenAI-compatible provider for generation and Tutor requests; each course requires consent, and only the minimum selected Repository Evidence is sent. The product has no account, synchronization, or telemetry.

## Planned Architecture

The product will run a local Node LTS process that opens a React browser UI. A single typed Hono workflow Interface owns Repository-Based Course behavior, while injected Adapters isolate Git cloning, OS credential storage, and remote AI. SQLite and FTS5 store local course data and the Repository Index; Course Snapshot clones stay in the local filesystem. Cancellable worker-thread jobs handle cloning, static analysis, and generation without blocking the UI.

| Area | Planned stack |
| --- | --- |
| UI | React, TypeScript, Vite, TanStack Router/Query, Tailwind CSS, Radix, React Flow, ELK |
| Local workflow | Node LTS, Hono, Server-Sent Events, worker threads |
| Persistence | SQLite, Drizzle ORM, SQLite FTS5, local filesystem |
| Repository analysis | `isomorphic-git`, TypeScript compiler API, `ts-morph` |
| AI and credentials | OpenAI JavaScript SDK, Zod, `keytar` |
| Testing | Vitest and Playwright |

## Architecture Diagrams

Open these native Excalidraw files in [Excalidraw](https://excalidraw.com/):

- [Local runtime and workflow seam](docs/architecture/01-local-runtime.excalidraw)
- [Repository-Based Course creation and Repository Index](docs/architecture/02-course-creation.excalidraw)
- [Learning flow](docs/architecture/03-learning-experience.excalidraw)
- [Tutor consent and minimal disclosure](docs/architecture/04-tutor-and-consent.excalidraw)
- [Local data lifecycle and recovery](docs/architecture/05-data-lifecycle-and-recovery.excalidraw)

## Design Records

- [Product specification](https://github.com/vkrana-me/asd/issues/1)
- [Domain glossary](GLOSSARY.md)
- [ADR-0001: Keep learning data local and require consent for remote AI](docs/adr/0001-local-first-consent-based-ai.md)
- [ADR-0002: Run the product as a local browser application with one workflow seam](docs/adr/0002-local-workflow-architecture.md)
