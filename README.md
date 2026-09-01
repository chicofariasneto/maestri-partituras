# Maestri Partituras

A version-controlled backup of [Maestri](https://maestri.app) canvas data: **partituras**
(saved canvas layouts/workflows) and **agent roles** (the custom agent prompts defined in
Settings → Agents). Maestri stores this data locally on each machine; this repo gives it
history, backup, and a shareable record across machines.

## What's in here

partituras/<partitura name>/<original-id-filename>.maestripartitura
roles/<role name>/role.json
.partitura-source   (gitignored — local paths to the Maestri data folders)

- **`partituras/`** — one folder per partitura, named exactly after the partitura's
  human-readable title. Inside is the original `.maestripartitura` JSON file, untouched,
  still named by its internal Maestri ID.
- **`roles/`** — one folder per agent role (Maestro, Builder, Reviewer, etc.), named
  exactly after the role's name. Inside is `role.json` with the role's color, icon, and
  full prompt text.
- Folder names track the *current* human-readable name; the file inside is matched by
  its internal ID, not by folder name — so a rename in Maestri renames the folder here
  too, it doesn't create a duplicate.

## How it stays in sync

A dedicated Maestri agent role — **Maestri Sync Git** — owns this repo. Its only job is
to read the local Maestri data (partitura files + role definitions), compare against
what's committed here, and create/update/rename folders as needed, then commit and push
to `main`. It touches nothing outside `partituras/`, `roles/`, and `.partitura-source`.


## Using this repo

- **Browse history**: `git log --follow -- "partituras/<name>"` or
  `roles/<name>` to see how a partitura or role evolved over time.
- **Restore an old version**: check out the file at an earlier commit and copy it back
  into your local Maestri data folder (paths recorded in `.partitura-source` on the
  syncing machine).
- **Diff a role's prompt** between two commits to see exactly what instructions changed.
- **Share a role or partitura**: point a teammate at the relevant folder — the file is
  the same JSON Maestri itself reads, so it's portable as-is.

## Notes

- `.partitura-source` is local and gitignored — it just points the sync agent at the
  right folders on that machine (Maestri's storage location can vary by install).
- Everything under `partituras/` and `roles/` is committed verbatim from Maestri's own
  files — nothing here is hand-edited or reformatted, so it should always match what
  Maestri itself would load.
