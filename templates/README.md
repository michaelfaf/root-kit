# Templates — install matrix

Six templates. Every one is annotated with HTML comments explaining what the section is for, what belongs in it, and what doesn't. **Those comments are the real content of this folder** — strip them only after the file is written, never before.

| Template | Installs as | Gated by | Always installed? |
|---|---|---|---|
| `STANDING-INSTRUCTIONS.md` | `CLAUDE.md` / `AGENTS.md` / custom-instructions box | **DP-1** (which file your platform reads) · **DP-6** (link + frontmatter style) | **Yes.** Nothing works without it. |
| `HOME.md` | `Home.md` at the workspace root | **DP-6** · **DP-7** (folder scheme — the map describes whatever scheme you keep) | Yes. Even a small workspace needs the Key Routes section, and the router needs somewhere to send "where is X" |
| `BUSINESS.md` | `Business.md` at the workspace root | **DP-2** (one workspace or split) · **DP-4** (numbers in-file or pointers) | Yes, if there's a business. Skip for a purely personal workspace. |
| `GOALS.md` | `Goals.md` at the workspace root | **DP-2** · **DP-4** | Yes |
| `ABOUT-ME.md` | `About-me.md` — location decided by **DP-2** | **DP-2** (this is the file that forces the split) · **DP-3** (seed or full) | Yes — at seed depth by default, unless DP-2 or DP-3 = C |
| `FOLDER-README.md` | A README in any folder that passes the three tests | **DP-5** (README depth) | No. It's a pattern applied on demand, not a file installed once. |

## Where the choices land

- **DP-1 → filename.** Same content either way. If both `CLAUDE.md` and `AGENTS.md` are in play, `AGENTS.md` holds the router and `CLAUDE.md` is one line: *"Read AGENTS.md — it has your instructions for this repo."*
- **DP-2 → location.** One workspace: all five at the root. Split: `Business.md` and `Goals.md` in the shared space, `About-me.md` in the private one, and the shared standing-instructions file routes to the business files only.
- **DP-3 → length of `ABOUT-ME.md`.** Seed = Block C questions 1-9 **plus question 13** (the unresolved tensions — short, and the highest-value answer in the block; its `Held, not solved` section is never optional); the three sections fed by Q10-12 (`Current state`, `When I'm stressed or overwhelmed`, `Never assume`) get stubbed with `_TBD_`, not deleted. Full = every section including the optional block.
- **DP-4 → what goes in the number-shaped slots.** In-file (A): the figure plus a verification date. Pointer (B): a line naming the system and how to pull it. Hybrid C: structure in-file, actuals fetched by the AI. Hybrid D: structure in-file, actuals named as a source the *user* opens. C and D are the same file; they differ only in who does the fetching, so say which in the line itself.
- **DP-5 → whether `FOLDER-README.md` gets used at all.** The three tests, README-everywhere, or nothing.
- **DP-6 → frontmatter and links.** Obsidian: keep the frontmatter blocks, use `[[wikilinks]]`. Plain markdown: delete the frontmatter, use `[text](relative/path.md)`.
- **DP-7 → what `HOME.md`'s folder list contains.** The template describes whatever scheme you already have. This kit does not restructure your folders.

## Rules for filling them in

1. **Never leave a `<placeholder>` in an installed file.** Either fill it or delete the line. A live root file with `<Your target>` in it teaches the AI that placeholders are acceptable content, and it will start producing them.
2. **Never invent an answer.** Anything the user didn't say gets `_TBD_` and a note in the wrap-up. A root file's whole value is that it's true.
3. **Every number carries the date it was stated.** Not the date you wrote the file — the date the person said it.
4. **Strip the comment blocks last**, after the file reads correctly with them in place. They're the specification; check your work against them before deleting.
