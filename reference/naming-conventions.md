# Naming conventions

## Items

| Item type | Pattern | Example |
| --- | --- | --- |
| Workspace | `<Domain>-<STAGE>` | `CryptoMarket-DEV` |
| Lakehouse | `lh_<layer or purpose>` | `lh_bronze` |
| Warehouse | `wh_<purpose>` | `wh_gold` |
| Notebook | `nb_<verb>_<object>` | `nb_load_bronze` |
| Data pipeline | `pl_<verb>_<layer>_<source>` | `pl_ingest_bronze_exchange` |
| Dataflow Gen2 | `df_<verb>_<object>` | `df_clean_trades` |
| Semantic model | `sm_<subject>` | `sm_market` |
| Report | `rpt_<subject>` | `rpt_market_overview` |
| Variable library | `vl_<scope>` | `vl_market` |

## Workspace folders

- Each item type has its own folder named `My_<ItemType>/` inside the workspace.
- For example, `My_Notebook/` contains Notebook items and `My_Lakehouse/` contains Lakehouse items.

## Pipeline activities

`<Verb> <object>` in title case, e.g. `Copy trades`.

## Tables and columns

- Tables and columns use `snake_case`.
- Technical metadata columns begin with `_`, e.g. `_load_ts`.
