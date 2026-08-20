# down-town

Public GitFlow repo for the Down_Town project. Default branch is `main`. Integration is `develop`.

## Clone

```powershell
git clone https://github.com/DatTran26/down-town.git
cd down-town
git checkout develop-<your-name>
git pull
```

Member branches: `develop-dat`, `develop-hieu`, `develop-kien`, `develop-thanh`.

Git cannot store `develop/<name>` while the integration branch `develop` exists, so personal branches use a hyphen.

## Branch map

```text
develop-<name>  →  PR  →  develop  →  release/x.y.z  →  main
```

- Work on your personal branch. Open PRs into `develop`.
- Never PR a personal branch into `main`.
- Cut `release/x.y.z` from `develop` when shipping. Hotfix from `main`.

See [AGENTS.md](AGENTS.md) for agent git-ops, [CONTRIBUTING.md](CONTRIBUTING.md) for humans, and [docs/README.md](docs/README.md) for docs. English commit fallback skills live in [`.claude/skills`](.claude/skills/README.md); skip them when `ak:git` is present.
