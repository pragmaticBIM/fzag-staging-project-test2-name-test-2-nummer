# Elementplan project repo template

Use this as a GitHub template repository. One repo = one project. **Repos may be public** — do not store access lists here.

## Structure

```
project.yaml         # project metadata
domains/
workflows/
elements/
values/
phases/
.github/workflows/publish.yml
```

## Setup

1. Create repo from this template in your GitHub org (public or private).
2. Edit `project.yaml` and add YAML entities under typed directories.
3. Add GitHub collaborators for editor write access.
4. Configure `access.json` on S3 via infra tooling (see `infra/access.example.json`).
5. Merge to `main` triggers publish workflow.

## Access control

- **Viewer login**: email OTP checked against `access.json` on S3 (`access/{project-slug}.json`) — not in this repo.
- **Editor write**: GitHub collaborator on this repo.

## CI

See `.github/workflows/publish.yml` for the artifact build skeleton.

Artifacts are data only (JSON, IDS, Excel). The viewer renders HTML at runtime.
