# af_portfolio_apps

Application workloads for the af_portfolio EKS cluster, deployed via ArgoCD.

## Overview

This repo is the GitOps source of truth for application workloads running on the
af_portfolio EKS cluster. ArgoCD discovers and deploys apps automatically via an
ApplicationSet in `af_portfolio_platform`.

## Repository Structure

```
af_portfolio_apps/
  apps/                 # One directory per application
    nginx/              # Example nginx workload
  README.md
```

## How it works

1. ArgoCD watches `apps/*` in this repo via an ApplicationSet in `af_portfolio_platform`
2. Each directory under `apps/` becomes an ArgoCD Application automatically
3. The namespace is created automatically matching the directory name
4. Merge to main triggers an automatic sync to the cluster

## Apps

| App | Namespace | Status |
|-----|-----------|--------|
| nginx | nginx | Example workload |

## Related Repos

- [af_portfolio](https://github.com/alfie-fielder/af_portfolio) — Terraform infrastructure
- [af_portfolio_platform](https://github.com/alfie-fielder/af_portfolio_platform) — ArgoCD platform config
- [af_portfolio_modules](https://github.com/alfie-fielder/af_portfolio_modules) — Reusable Terraform modules
