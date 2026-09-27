# Fabric environment

## Tenant

- **Tenant ID**: `370fa88c-de52-4400-b6cd-027ef6a8ddf2`
- **Agent identity**: service principal, app ID `b593a632-afcd-4c1b-b0bd-43080c0317ab` (no credentials here)

## Scope

| Workspace | ID | Stage | Agent may write? |
| --- | --- | --- | --- |
| CryptoMarket-DEV | `89c341b0-55ba-4b20-ac0f-18de88049aad` | DEV | Yes, after a dry run and confirmation for each write |

Every other workspace is read-only. `fab ls` under this identity listed only `CryptoMarket-DEV`. Visibility is verified; the Contributor role has not been tested by a write and should be checked in Manage access if needed.
