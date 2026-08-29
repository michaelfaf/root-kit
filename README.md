# Root Kit

The root of an AI second brain: a standing-instructions file that **routes**, plus the four files it routes to — a map, the business, the goals, and you. Your AI interviews you and writes them. Extracted from a working setup and adapted to yours, not copied onto it.

## Read this first — what this is and why

**The problem.** Your AI assistant starts every session knowing nothing about you. So you write an instructions file. It helps for a month, then it's 4,000 words, it gets loaded into every session including the trivial ones, and it *still* doesn't have the section you needed — because the sections worth having are deep, and deep is exactly what won't fit in a file that's read on every turn. The file that's always loaded has to be short. The context you need is long. Both are true.

**What this installs.** The split that fixes it. Your standing-instructions file stops holding the depth and starts pointing at it: a short router with your rules, your boundaries, and a table saying which kind of question goes to which file. Then four files hold the actual depth — `Home.md` (where everything lives), `Business.md` (how the business really works, including the things outsiders get wrong), `Goals.md` (targets and this quarter's priorities), `About-me.md` (how you decide, where you're blind, how you want to be pushed back on). Plus a rule for when a folder earns a README and when it earns nothing.

**Why it works.** Depth costs you nothing until it's needed, so it's allowed to be deep. And an AI reads a route — it isn't searching your notes and half-finding something, it's told where the answer lives. Each fact ends up with exactly one home.

**The part that makes it usable:** your AI **interviews you** and writes the files from your answers. Nobody fills these in well from a blank page. Answering *"what are the three things an outsider gets wrong about your business that would make their advice useless?"* is easy. Staring at a heading called "Business Model" is not.

**Use it if:** you've explained your business to an AI more than three times · your instructions file has quietly grown past a thousand words · you get advice that's correct in general and wrong for you · you want a new session, or a new tool, to be useful in the first thirty seconds.

**It is not** a note-taking system, a prompt library, or tied to any vendor. Five markdown files and a habit. It deliberately does not reorganize your folders.

**→ Want the full picture before deciding? Read [OVERVIEW.md](OVERVIEW.md)** — every concept defined, how the install actually goes, your role versus your AI's, in about ten minutes.

## How to use this kit

**If you use an AI coding assistant** (Claude Code, Codex, Cursor, Cline, Copilot, Amp):

1. Clone or download this repo.
2. Open it with your assistant and say: **"Read IMPLEMENT.md and walk me through it."**
3. It scans your setup, walks you through seven decisions, interviews you, writes your root files, wires them in, and proves the result with a cold-read test. Progress lives in `STATUS.md`, so a dead session doesn't cost you the hour.

Recommended model: the most capable one you have, at high reasoning effort (Claude Fable 5 high, or Claude Opus high). The interview is the part that suffers most on a weaker model — the follow-up questions are where the good material comes from.

**If you use a chat AI** (claude.ai, ChatGPT, Gemini) without file access:

1. Paste `IMPLEMENT.md` into a chat, then `INTERVIEW.md` when you reach Phase 2.
2. Say: "Walk me through this. I'll create the files by hand as you go."
3. Keep `STATUS.md` yourself in a note and paste it back at the start of each new chat.

**If you have no AI assistant:**

Read `INTERVIEW.md` and answer the questions into a document, then fill in `templates/` from your answers. Slower, and you'll miss the follow-up questions that do half the work — but every step is doable by hand. `examples/` shows you what finished looks like.

## Time

About an hour for all four interview blocks, plus fifteen minutes of decisions and setup. You can stop after any block — the files work half-built, and the personal one is *supposed* to start thin.

## What's in here

| File | What it is |
|---|---|
| `OVERVIEW.md` | The full explanation — read this first to understand the system before installing |
| `IMPLEMENT.md` | The setup walkthrough: scan, seven decisions, interview, install, live test (written for your AI, readable by you) |
| `INTERVIEW.md` | The question bank — the heart of the kit. Four blocks, 38 questions plus follow-ups, and the rules for asking them |
| `STATUS.md` | Progress checklist — your AI ticks it off and records your decisions here |
| `templates/` | The six file templates, annotated section by section with what belongs and what doesn't |
| `examples/fictional/` | A complete filled-in set for an invented company — what "done" looks like |
| `examples/live-vault/` | Two real root files from the workspace this was extracted from, unedited |
| `AGENTS.md` / `CLAUDE.md` | Entry points so coding agents orient themselves when they open this repo |

## The seven decisions

Your AI walks you through each with trade-offs and a recommendation:

1. **Which file holds the router** — `CLAUDE.md`, `AGENTS.md`, both, or a custom-instructions box
2. **One workspace or split** — personal separate from anything a teammate can reach
3. **How much of `About-me.md` to write now** — seed, full, or skip
4. **Numbers in the file or pointers to where they live**
5. **README depth** — the three tests, everywhere, or nowhere
6. **Obsidian-native or plain markdown**
7. **Whether to restructure your folders** — the recommendation is no, and the kit explains why

## What you end up with

- A standing-instructions file under a thousand words that routes instead of containing
- Four root files holding the depth, written in your words, with nothing invented
- A business file whose best section is the list of things outsiders get wrong about you
- A personal file whose best section is how you want to be pushed back on
- A rule for when a folder earns a README, so you stop writing ones nobody reads
- A test you can re-run any time: a fresh session, given only the router, answers five questions about your business and you — correctly
