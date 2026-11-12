# Imp Workbench

Development environment for integrating Imp repos together — not an Imp implementation.

Mounted siblings:

- [imp-spec](https://github.com/silentorb/imp-spec) — language-neutral specs
- [imp-ts](https://github.com/silentorb/imp-ts) — TypeScript implementation
- [imp-rs](https://github.com/silentorb/imp-rs) — Rust implementation

## Setup

1. Copy `.devcontainer/.env.example` to `.devcontainer/.env`.
2. Set `IMP_RS_PATH`, `IMP_TS_PATH`, and `IMP_SPEC_PATH` to your local sibling checkouts (paths relative to `.devcontainer/`, or absolute).
3. Open this folder in Dev Containers.

Services: `workbench`, `imp-rs`, and `imp-ts`. Sibling repos appear under `.mnt/`.

## Agent docs

See [`AGENTS.md`](./AGENTS.md). Planning and publishing skills come from silentorb-agents packages baked into the workbench image (`/opt/silentorb-agents/`); rebuild the workbench image to bump package versions.

## License

[MIT](./LICENSE)
