# Agent guide

- Preset: gitflow
- Visibility: public
- Default branch: main
- Integration branch: develop
- Member branches:
  - Dat → `develop/dat`
  - Hieu → `develop/hieu`
  - Kien → `develop/kien`
  - Thanh → `develop/thanh`
- PR target: develop (personal). Never personal → main.
- release/x.y.z → main. hotfix/* from main.
- Git ops:
  - Prefer ak:git cp / ak:git pr develop / ak:ship beta if present
  - Else: principled-git-commit + caveman-commit + wpc git-fallback
- License: mit
- Security file: SECURITY.md on
- Environments: staging, production (no deploy secrets in v1)
- Releases: cut release/x.y.z from develop, merge to main, then scripts/create-release.ps1 or ak:ship official
- Do not commit .env or secrets

## Branch map

```text
develop/dat | develop/hieu | develop/kien | develop/thanh
    →  PR  →  develop  →  release/x.y.z  →  main
```

Never PR a personal branch to `main`. Feature work starts from `develop` as `feature/<slug>` or from a member branch.

## Git-ops policy

1. Identity: `ensure-git-identity.ps1` (noreply `id+login@users.noreply.github.com`). Do not set global git user.
2. If this runtime has `ak:git`: `ak:git cm` / `ak:git cp` / `ak:git pr develop`. Secret scan + split + message + push live in ak:git. Do not also load principled or caveman.
3. If `ak:git` is missing: principled-git-commit (atomic, block secrets) → caveman-commit (≤50, no emoji, no AI trailer) → wpc git-fallback.
4. Personal/feature → `develop` only. `release/x.y.z` → `main`. Hotfix from `main`.
5. Do not force-push `main` or `develop`.
