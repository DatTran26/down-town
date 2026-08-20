# Commit dialect

- Language: English subjects and bodies. No Vietnamese or other native-language prose in git history.
- If runtime has `ak:git`: follow ak:git commit-standards (conventional, <72, no AI trailer). Do not load the vendored skills.
- Else: `.claude/skills/principled-git-commit` (atomic + secrets) then `.claude/skills/caveman-commit` (≤50, no emoji, no AI trailer).
- Inverse rule: everything outside this file is English. Do not add a native-language whitelist unless a proper noun has no stable English form.
