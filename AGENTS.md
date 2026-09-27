<!-- fabric-engineering-skills:start -->
# Fabric brain

This repository carries the conventions and guardrails for CryptoMarket Microsoft Fabric development. Read this file at the start of every session. It is the canonical instruction file for AI tools working in this folder.

## Start of session

Before Fabric work, read the relevant files under `reference/`. Use their exact names and conventions; call out contradictions before acting.

## Guardrails

- **Scope.** Only `CryptoMarket-DEV` may be changed. Every other workspace is read-only. Changing this scope requires an explicit update to these guardrails first.
- **Dry run and approval.** Before any write, show the exact commands or definition changes and their effects; dry-run when possible. Obtain confirmation for every write.
- **Destructive changes.** Never delete, overwrite, move or change permissions without explicit confirmation for that specific operation. Never use `fab rm --hard`. Use `-f` only for an explicitly approved import.
- **Secrets.** Never print, log or store tokens, passwords, client secrets or credential-bearing connection strings. Do not run commands that print access tokens.
- **Identity.** Use the agreed service principal for both `fab` and Fabric MCP. Sign-in is verified in tenant `370fa88c-de52-4400-b6cd-027ef6a8ddf2`; treat everything that identity can see as sensitive.

## Verify before you claim

Verify claims about Fabric features, settings, APIs and limits against Microsoft Learn via `microsoft-learn`, and cite the page. Say when verification is unavailable.

## Build, verify, test

Use `build-in-fabric` when available. Otherwise plan from `reference/`, obtain approval, build only in the writable workspace, verify items with read-only commands, then offer an end-to-end test and report its result.

## Keep the brain current

Record durable facts and corrections in the appropriate `reference/` file in the same turn, without secrets. Use `fabric-brain` when available.

## Reference

- `reference/environment.md`: tenant, workspace scope and identity
- `reference/naming-conventions.md`: item, folder, table and column naming
- `reference/fabric-cli.md`: CLI usage and verified local details
- `reference/architecture/`: add a file only when a real pattern is described

## Folders

- `data/`: development samples only; never production or personal data.

## Tools

- **Fabric CLI** (`fab`): inspect and change Fabric items, subject to the guardrails. See `reference/fabric-cli.md`.
- **Microsoft Learn MCP** (`microsoft-learn`): current Microsoft documentation.
- **Fabric MCP** (`fabric-mcp`): item schemas and read-only Fabric access. Make changes through `fab`; check item definitions against `docs_item-definitions` before writing them.
- **Microsoft `fabric-skills` plugin**: specialized Fabric skills and remote MCPs when installed.
<!-- fabric-engineering-skills:end -->
