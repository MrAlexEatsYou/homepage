# Agents — homelab app repo

This repo is part of the **MrAlexEatsYou** homelab GitOps layout.

## Read first

- **Cloud agents / GitHub + MCP:** [`homelab-ops` CLOUD_AGENT_RUNBOOK](https://github.com/MrAlexEatsYou/homelab-ops/blob/main/docs/CLOUD_AGENT_RUNBOOK.md)
- **Ownership:** [`OWNERSHIP_MAP`](https://github.com/MrAlexEatsYou/homelab-ops/blob/main/docs/OWNERSHIP_MAP.md)

## This repository

See the **README** and **`.github/workflows/`** for this service’s scope (build, dispatch, or both). Compose and deploy reconciliation live in **`homelab-ops`** (`platform/apps/`, `pipelines/deploy-configs.sh`).

## Secrets & verification

- If this repo dispatches to ops, configure **`HOMELAB_OPS_TOKEN`** (GitHub → Settings → Secrets and variables → Actions). Verify: workflow **Publish Dispatch** or **App CI** succeeds and **`homelab-ops` → Update App Pin** runs.
- Server runtime env files are rendered from secrets on **`homelab-ops`** during **Deploy Configs** — not from this repo.

## MCP

Bridge/server source: [`MCP_GITOPS.md`](https://github.com/MrAlexEatsYou/homelab-ops/blob/main/docs/MCP_GITOPS.md). No MCP secrets belong in this repository.

## Central logs (operators)

Docker logs are aggregated in **Grafana/Loki** from **`homelab-ops`** only — you do not add logging code to this repo. See [`OBSERVABILITY_GITOPS.md`](https://github.com/MrAlexEatsYou/homelab-ops/blob/main/docs/OBSERVABILITY_GITOPS.md).
