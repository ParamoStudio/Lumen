# Lumen — Find Anything
<img width="512" height="512" alt="lumen" src="https://github.com/user-attachments/assets/4ff026a3-034e-49ad-bd26-8b8ce1fa3191" />


Scoped fuzzy file search across the folders you actually work in. Jump into a favorite
folder with a shortcut and find anything inside instantly without opening Finder or
clicking through subfolders. Plenty of tools available to find anything fast with minimal typing.

Quick view, copy path and show in finder commands with just one hand, too!

Lumen **navigator first, search second**: enter a workspace and you see its top level,
like opening the folder; start typing and it becomes a recursive fuzzy search scoped to
that folder.

Want to find anything else? Just type h + space and you are searching freely.

## Features

- **Workspaces** — pin your favorite folders (disciplines, projects, asset libraries) and
  enter one by typing its alias (or number) + space, e.g. `cr ` for Ceramica.
- **Fast fuzzy search** — powered by `fd` (indexing) and `fzf` (ranking). Sub-second on
  scoped folders.
- **A small, sharp grammar** in the search bar:
  - `term1 term2` — fuzzy terms, ANDed, path-aware.
  - `.pdf` `.mp4` — filter by extension (OR).
  - `-d` `-a` `-v` `-i` … — filter by category (editable groups of extensions).
  - `--dc` `--dm` `--big` `--small` — order by created/modified date or size.
  - `--dc,2024` `--dc,mar` `--dc,week` — date arguments (year, month, today/week/month/year),
    combinable and order-free: `--dc,mar,2024`.
- **Home mode** — type `h ` to fuzzy-search your whole home folder (`~`), with the same
  grammar and keyboard. Streams `fd | fzf` so a huge tree never lands in memory; configured
  workspaces are excluded by default so Home stays out of your scoped corpus.
- **Keyboard, one-handed** — `↵` open · `⌘C` copy the containing folder · `⌘⇧C` copy the
  full path · `⌘F` reveal in Finder · `⌘D` Quick Look · `⌘R` refresh the index.
- **Fully configurable** — categories, order tools (codes + enable/disable) and date-filter
  keywords are all editable in *Manage Tools*. Because everything is a code you rename,
  the grammar needs no translation.
- **Portable config** — export your whole setup to a self-documenting JSON (back it up,
  move it to another machine, or hand it to an AI to understand your organization), and
  import it back.
- **Bilingual UI** (English / Español) with importable language packs.

## Requirements

- **macOS** (Apple Silicon). Lumen ships the `fd` and `fzf` binaries — no setup, no network
  at runtime.

## How it works

`fd` walks the scope once on entering and the list is cached for the session; each keystroke
filters that list with `fzf`'s native scoring, on top of which Lumen layers a structure-aware
ranking (folders first, matches in earlier path segments first, prefix > contains > scattered).
Nothing is indexed in the background and nothing runs as a daemon.

## Setup

1. **Manage Workspaces** — add a folder, give it a name and one or more aliases.
2. Open **Lumen**, type your alias + space, and search.
3. Optionally open **Manage Tools** to tweak categories, order tools and date filters, or
   switch the UI language in the extension preferences.

---

Made by **Páramo Studio**. Open source — explore the code and other projects (Óculo,
Páramo Kiln Monitor, and more) on [GitHub](https://github.com/ParamoStudio).
