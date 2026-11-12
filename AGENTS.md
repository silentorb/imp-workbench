# AGENTS Guide — Imp Workbench

## Repository purpose

This repo is a **development environment to integrate Imp repos** in one Dev Container stack. It is **not** an Imp implementation.

Sibling checkouts are bind-mounted under `.mnt/`:

| Mount | Repo | Role |
| --- | --- | --- |
| `.mnt/imp-spec/` | [imp-spec](https://github.com/silentorb/imp-spec) | Language-neutral specs |
| `.mnt/imp-ts/` | [imp-ts](https://github.com/silentorb/imp-ts) | TypeScript implementation |
| `.mnt/imp-rs/` | [imp-rs](https://github.com/silentorb/imp-rs) | Rust implementation |

Follow each mounted repo’s own `AGENTS.md` when editing Imp there.

## Cross-repo Imp changes

When making **functional** Imp changes, update **spec and implementations in the same change** (`imp-spec` plus `imp-ts` and/or `imp-rs` as applicable). Do not leave one side behind.

Stay **vigilant for feature drift** across mounted repos (docs vs TypeScript vs Rust). Prefer reconciling divergence in the same task when it is in scope; call out any remaining drift explicitly.

## Workbench scope

Workbench-owned files are `.devcontainer/` and `docker/`. Change those for environment/tooling work. Edit Imp only under `.mnt/imp-{spec,ts,rs}` when the task is Imp itself.

## Installed agent packages

Silentorb agent skill packages are baked into the workbench image under `/opt/silentorb-agents/`. Skills are exposed via `.agents/skills/` symlinks. Follow each package’s `AGENTS.md`:

| Package | AGENTS.md |
| --- | --- |
| `silentorb-agents-publishing` | [`/opt/silentorb-agents/silentorb-agents-publishing/AGENTS.md`](/opt/silentorb-agents/silentorb-agents-publishing/AGENTS.md) |
| `silentorb-agents-planning` | [`/opt/silentorb-agents/silentorb-agents-planning/AGENTS.md`](/opt/silentorb-agents/silentorb-agents-planning/AGENTS.md) |

## Plan verification

| Repo | Full verify |
| --- | --- |
| workbench (this repo) | none — tooling/docs only |
| `.mnt/imp-spec/` | see that repo’s `AGENTS.md` |
| `.mnt/imp-ts/` | see that repo’s `AGENTS.md` |
| `.mnt/imp-rs/` | see that repo’s `AGENTS.md` |

When Imp repos are in plan scope, use each mounted repo’s own verify docs. Do not invent Imp verify commands here.

## Conventions

- Keep `.devcontainer/.env` local; do not commit it (`.env.example` is the template).
- Do not commit `.mnt/` (bind mounts, not source of this repo).
- Prefer focused Dockerfile / compose changes; avoid unrelated refactors.
