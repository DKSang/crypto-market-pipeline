# Fabric CLI notes

- **Verified version**: 1.7.0.
- **Signed in as**: service principal, app ID `b593a632-afcd-4c1b-b0bd-43080c0317ab` in tenant `370fa88c-de52-4400-b6cd-027ef6a8ddf2` (`fab auth status` succeeded; no credentials here).
- **Docs**: https://aka.ms/fabric-cli. Run `fab <command> --help` before using a command for the first time in a session; flags change between versions.

## Paths

- Workspace: `"<Workspace name>.Workspace"`; item: `"<Workspace>.Workspace/<Item>.<Type>"` (e.g. `"CryptoMarket-DEV.Workspace/lh_bronze.Lakehouse"`).
- Quote every path; names can contain spaces.
- Lakehouse content: `.../<Lakehouse>.Lakehouse/Files/...` and `.../<Lakehouse>.Lakehouse/Tables/<schema>/<table>`.
- Put each item in its type's `My_<ItemType>/` workspace folder as specified in `reference/naming-conventions.md`. Check `fab` help for folder-aware commands before use.

## Everyday commands

| Task | Command |
| --- | --- |
| List workspaces / items | `fab ls` / `fab ls "<ws>.Workspace" -l` |
| Does it exist? | `fab exists "<ws>.Workspace/<item>.<Type>"` |
| Properties (IDs etc.) | `fab get "<ws>.Workspace/<item>.<Type>" -q id` |
| What can I do with this? | `fab desc .<Type>` |
| Export a definition to local files | `fab export "<ws>.Workspace/<item>.<Type>" -o ./<folder>` |
| Create a lakehouse with schemas | `fab mkdir "<ws>.Workspace/<lh>.Lakehouse" -P enableSchemas=true` |
| Upload a local file | `fab cp ./data/<file> "<ws>.Workspace/<lh>.Lakehouse/Files/<path>/<file>"` |
| Import a definition folder | `fab import "<ws>.Workspace/<item>.<Type>" -i <folder> -f` (notebooks in `.py` format: add `--format .py`) |
| Start a job, then poll | `fab job start "<path>"`, `fab job run-list "<path>"`, `fab job run-status "<path>" --id <job-id>` |
| Raw REST call | `fab api -X get workspaces` |

## Gotchas

- `fab import` asks "Are you sure?", which the agent's shell can't answer: it needs `-f`, used only for an approved import.
- `fab job run --timeout N` cancels the job when the timeout hits (config `job_cancel_ontimeout`, default true). For long jobs use `fab job start` and poll.
- Notebook import defaults to `.ipynb`; a `notebook-content.py` folder needs `--format .py`.
