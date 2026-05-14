# CloudOps Platform Runbook

## How to Rollback a Deployment via GitOps

### When to use this
- Bad image deployed, pods crashing
- Config change broke the app
- Need to revert to last known good state

### Steps

**Step 1 — Find the bad commit**
```bash
git log --oneline manifests/api/deployment.yaml
```

**Step 2 — Revert it**
```bash
git revert <bad-commit-hash>
git push origin main
```

**Step 3 — ArgoCD auto-syncs**
