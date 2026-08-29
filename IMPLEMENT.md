# IMPLEMENT — the root of an AI second brain

> **AI: this file is addressed to you.** You are installing a set of root files for your user, written from an interview you conduct with them, adapted to their environment. Work the phases in order. Tick every task in `STATUS.md` as you complete it and record every decision in its Decisions table — that file is how a future session resumes if this one dies. A human without an AI can do every step by hand.

## What you are installing

A standing-instructions file that **routes**, plus four root files that **hold the depth**.

| File | Job | Read when |
|---|---|---|
| `CLAUDE.md` / `AGENTS.md` | The router. Identity, rules and boundaries, decision protocol, and a table mapping intents to depth files. Small on purpose. | **Every session, automatically** |
| `Home.md` | The map — where everything lives. Folders and load-bearing files, never leaf notes. | Navigating, or lost |
| `Business.md` | The canonical model — customers, pricing mechanics, margin structure, the rules outsiders get wrong. | Any business-model question |
| `Goals.md` | Target state — this year's number, the quarter's priorities, the cadence, the risks. | Anything about priority or direction |
| `About-me.md` | The person — purpose, blind spots, how they want to be pushed back on, decision style. | Coaching, hard calls, "am I being an idiot here" |

…plus **the README rule**: a folder earns a README only when it's a navigation hub, its purpose isn't obvious from the name, or it carries conventions a newcomer would miss.

**The mechanism in one line:** the always-loaded file stays small by *pointing* at depth instead of containing it, so the AI arrives at every session with the operating contract and pulls the rest only when the work calls for it.

**Why not just put it all in one file?** Because that file gets loaded into every session, every turn. A 6,000-word standing-instructions file spends your context on the business model when you asked it to rename a variable, and it still won't have the section you actually needed. Routing is what lets the depth be deep.

**What makes this different from a pile of notes:** the router. Notes an AI has to search are notes it will half-find. A table that says *"coaching questions → `About-me.md`"* means the right file gets read on the right turn, and one fact lives in exactly one place.

---

## Phase 0 — Environment scan

Before asking the user anything, find out what you're working with. Record findings in `STATUS.md` → Scan results.

1. **What am I?** Your own platform (Claude Code / Codex / Cursor / Cline / Copilot / chat-only / other), and whether you can: read and write files, run shell commands, spawn subagents, persist memory across sessions.
2. **Which standing-instructions file does my platform actually read, and at what scope?** Claude Code reads `CLAUDE.md` (project root, plus `~/.claude/CLAUDE.md` globally). Codex, Cursor, Amp, Copilot and several others read `AGENTS.md`. Cursor also reads `.cursor/rules/*.mdc` files, which are scoped per-glob rather than global. Chat-only tools have a custom-instructions box with a character limit. **Scope matters more than filename**: a workspace-scoped file only fires when that workspace is open, and you must tell the user that.
3. **Where does the user's work live?** An Obsidian vault, a notes folder, a git repo of documents, a Drive folder. Look before you ask. If nothing is visible from where you're running, ask.
4. **What's already at the root?** Read every existing instructions file, README, or notes-about-notes file **in full** before you write anything. You are merging into their conventions, not bulldozing them. If they already have a `CLAUDE.md` with rules in it, those rules survive — you're adding a router around them, not replacing them.
5. **Is this Obsidian?** Look for a `.obsidian/` directory. It decides DP-6.
6. **How many top-level folders?** Note the count. **Write `Home.md` anyway** — even at four folders it carries the Key Routes section, which is the part people actually use, and the router needs somewhere to send "where is X." Skip it only if the user, told the trade-off, says they'd rather not have the file.

**Chat-only fallback:** if you can't see their file system, you'll narrate and they'll create. Everything below still applies. `STATUS.md` lives in a note they paste back to you at the start of each session, and the four root files live wherever they keep documents. Say this out loud so they know what they're signing up for.

Then tell the user, in one paragraph, what this kit installs, and confirm they want to proceed.

---

## Phase 1 — Decisions

Present each one conversationally: context, options with trade-offs, your recommendation adjusted by what the scan found. Record each choice in `STATUS.md` before moving on. Some users will say *"whatever you recommend"* — that's fine, take the recommendation, but say which one you took and why, and record it.

### DP-1 — Which file are these instructions going in?

**Options:**
- **A. `CLAUDE.md`** — read automatically by Claude Code and Claude Desktop projects. *Trade-off:* Claude-only; other tools ignore it.
- **B. `AGENTS.md`** — the emerging cross-tool convention, read by Codex, Cursor, Amp, Copilot and others. *Trade-off:* Claude Code doesn't read it by default.
- **C. Both** — `AGENTS.md` holds everything; `CLAUDE.md` is one line: *"Read AGENTS.md — it has your instructions for this repo."* *Trade-off:* two files, but one source of truth and no drift.
- **D. The platform's custom-instructions box** — for chat-only tools with no file access. *Trade-off:* character-limited, so only the router fits; the depth files get pasted in on demand.
- **E. A native per-tool rule file** — Cursor's `.cursor/rules/*.mdc` with `alwaysApply: true`, or your platform's equivalent. *Trade-off:* it genuinely always fires in that tool and nowhere else, so it's the most reliable option for one tool and invisible to every other.

**Recommendation:** **C** if the scan found any file-capable coding agent, even one — it costs one extra line and it means the root survives you switching tools next year, which people do more often than they expect. **A** if they're certain they'll only ever use Claude tooling. **D** only if there's genuinely no file access.

**If the scan found Cursor specifically:** take **C *plus* E** — put the router in `AGENTS.md` and add a one-line always-apply `.mdc` that says *"Read AGENTS.md at the start of every session."* Cursor's own mechanism is the thing that reliably fires; `AGENTS.md` is what keeps the content portable to the next tool. Don't put the router content itself in the `.mdc`, or you've locked it to one editor.

**Scope warning, all options:** if your platform's instructions file is workspace-scoped, it only fires when that workspace is open. Put it where the work lives, and tell the user which sessions will and won't see it. A user who thinks their rules are global and finds out they weren't loses trust in the whole system.

### DP-2 — One workspace, or split personal from shared?

**Options:**
- **A. One workspace** — everything at one root: business, goals, projects, and the personal file. *Trade-off:* the moment anyone else needs the business context, they can reach the personal file too.
- **B. Split** — a private workspace with `About-me.md` and personal projects, and a shared space holding `Business.md`, `Goals.md`, and the team-facing standing-instructions file. *Trade-off:* two roots to maintain, and business facts have exactly one home or they drift.
- **C. Business-only** — no `About-me.md` at all. *Trade-off:* you lose the file that does the most to change how the AI actually behaves.

**Ask, don't infer.** The deciding fact is not visible to your scan — it lives in the user's head. Ask both:
> 1. *"Will anyone else — a teammate, an assistant, a co-founder — ever point their AI at this folder?"*
> 2. *"Is this folder inside anything that syncs or is shared?"* (iCloud Desktop, Dropbox, Google Drive, a team repo.) Check the path yourself if you can; a personal file in a synced folder is shared whether or not anyone intended it.

**Recommendation:** **B if either answer is yes; A if both are no.** Start at A if they genuinely don't know — it's the cheaper mistake to fix, and `About-me.md` is one file to move. If the user says "whatever you recommend," ask the two questions first: this is not a decision you can take on their behalf without them.

The thing to know going in: **`About-me.md` is what forces the split later.** It's the file that makes the system work and the file you can't share. When a teammate first needs the business context, that's the split, and it's a good problem — it means the root got used.

### DP-3 — How much of `About-me.md` to write now?

**Options:**
- **A. Seed** — 20 minutes: purpose, strengths, blind spots, how to push back, decision style, numbers fluency. Roughly Block C questions 1–9. *Trade-off:* thin at first; several sections are stubs.
- **B. Full** — the whole of Block C plus the optional sections, in one sitting. Budget two hours and expect it to be draining. *Trade-off:* long, and half of what you write on day one is guesswork about yourself.
- **C. Skip for now.** *Trade-off:* the AI advises a generic person in your situation instead of you, which is most of what you were trying to fix.

**If C (or DP-2 = C): four other things change, and you must do all four** — otherwise the install ships with a routing line pointing at a file that doesn't exist:
> 1. Delete the `About-me.md` row from the router's routing table.
> 2. Move the push-back rules into the router's "Rules & boundaries" section instead — that part is too valuable to lose, and it fits in three bullets. Ask Block C questions 4, 5 and 7 anyway, even if nothing else in Block C gets asked.
> 3. Skip question 4 of the Phase 4 cold-read test, and record in `STATUS.md` that the personal layer is not installed and therefore not tested.
> 4. Drop the first of the three Phase 5 habits and keep the other two.

**If A (the recommendation): three non-optional template sections have no interview question behind them** — `Current state`, `When I'm stressed or overwhelmed`, and `Never assume` come from Block C questions 10-12, which sit outside the seed. Stub all three with `_TBD_` and a one-line note saying they fill in as things happen. Do not delete them: they are the sections most likely to earn their keep in month two, and an empty heading with a reason attached is an invitation, where a missing heading is a decision the user never made.

**Recommendation:** **A**, and this isn't hedging. The seed is enough to change AI behavior on day one — push-back rules and decision style do most of the work. The best entries in this file come from friction that hasn't happened yet: the gate that's actually worth having is the one written the week after you did the thing you keep doing. Set the habit instead: **when a session goes wrong in a way that's about you rather than the work, that's an `About-me.md` entry.** Tell the user that line explicitly; it's the whole retention mechanism.

### DP-4 — Does the file hold the numbers, or point at where they live?

**Options:**
- **A. Numbers in the file**, each with a verification date. *Trade-off:* they go stale, and a stale number stated confidently is worse than no number at all — you'll act on it.
- **B. Pointers only** — the file describes the mechanics, and the AI pulls live figures from the CRM, accounting system, or spreadsheet. *Trade-off:* requires that the AI can actually reach that system, and every question costs a lookup.
- **C. Hybrid, AI-fetched** — targets and structural facts in the file; per-customer, per-month, and live actuals pointed at, and *you* pull them.
- **D. Hybrid, human-fetched** — same split, but the file names the system as a source the **user** opens, because you can't reach it. *Trade-off:* the AI can't answer a live-number question alone; it tells them where to look.

**Recommendation — read the condition, not the letter.** Ask one question the scan can't answer for you: *"Can I actually reach that system from here?"* Then:
> - **A real system of record you can read** (an API, a synced export, a file on disk) → **C**.
> - **A real system of record you cannot read** — Stripe, QuickBooks, a CRM behind a login, a Google Sheet you have no access to → **D**. *This is the common case for a small business, and it is not option A.* Pin structure and targets in-file with dates; name the system explicitly as a human-fetch source so neither of you mistakes a pinned number for a live one.
> - **No system of record at all** — the numbers live in a spreadsheet nobody has opened since March → **A**, with disciplined verification dates, and say plainly that the dates are the only thing keeping the file honest.

**If the user says "whatever you recommend," the answer is whichever of C/D/A the condition above selects for their scan** — never a default letter. Say which one you took and why.

The rule underneath: **pin what's structural, point at what's live.** How you charge is structural. What this customer pays is live. Your quarterly target is structural for the quarter. Last month's revenue is live.

### DP-5 — Which folders get a README?

**Options:**
- **A. The three tests** — a folder earns a README only when it's (a) a navigation hub with real routing to do, (b) non-obvious in purpose from its name, or (c) carrying conventions or gotchas a newcomer would miss. Skip homogeneous leaf folders: transcripts, attachments, archives, daily notes, exports. *Trade-off:* you have to make a judgment call each time.
- **B. README everywhere** — consistent, no judgment needed. *Trade-off:* most of them say nothing, they rot, and an AI reads every one of them.
- **C. None** — rely on folder names. *Trade-off:* fine until a folder has subfolders or a convention, then someone guesses wrong.

**Recommendation:** **A**, with the guard stated out loud: *if every section you'd write would just restate the folder name plus a directory listing, write nothing.* B fails not because it's expensive to write but because an unread README that has gone wrong actively misinforms — it's the one that gets believed. Update trigger is **structure, purpose, or conventions changed** — never individual file edits. Template and full rule: `templates/FOLDER-README.md`.

**If B or C:** delete the "READMEs" bullet from the router template's "Operational pointers" section — it states rule A. For B, replace it with the user's actual rule ("every folder gets a README with purpose and contents"). For C, delete it and skip Phase 3c.

### DP-6 — Obsidian-native or plain markdown?

**Options:**
- **A. Obsidian-native** — YAML frontmatter, `[[wikilinks]]`. *Trade-off:* wikilinks don't resolve on GitHub, in most editors, or for an AI that isn't told how to expand them.
- **B. Plain markdown** — `[text](relative/path.md)` links, no frontmatter. *Trade-off:* you lose Obsidian's graph view, backlinks, and property queries.
- **C. Minimal hybrid** — three frontmatter keys (`type`, `read_first`, `updated`), plain relative links. *Trade-off:* the graph view is thinner than it could be.

**Recommendation:** **A if the scan found a `.obsidian/` directory and the files stay in the vault** — the backlinks are a real part of why an Obsidian root works, and any competent AI resolves `[[Business.md]]` to the file of that name. **B otherwise.** Choose **C** if any of these files will ever be read outside the vault — pushed to a repo, shared with a teammate on a different tool, rendered on the web. Whichever you pick, be consistent: half-wikilinked files are the ones that break.

### DP-7 — Do you restructure the folders too?

The workspace this kit came from organizes its top level by business function — an accountability chart turned into folders, one per role: sales and marketing, operations, technology, finance, people, strategy. It works well once there are real departments and real owners, because every folder has exactly one person who should be in it.

**Options:**
- **A. Keep the folder scheme you have.** Add the root files; `Home.md` describes whatever's already there. *Trade-off:* if the current scheme is genuinely bad, you've made a good map of a bad building.
- **B. Restructure to a function-based scheme now.** *Trade-off:* two changes at once, and if the root doesn't stick you won't know which one failed.
- **C. Some other scheme** — PARA, a lifecycle split, whatever fits.

**Recommendation:** **A.** The root files work on any folder scheme — that's the point of `Home.md`. Restructuring at the same time as installing a new convention doubles the failure surface and halves what you learn. **This kit deliberately does not install a folder scheme.** If the current structure turns out to be the problem, that's a separate job, done later, with the map already written to make it easy.

---

## Phase 2 — The interview

**This is the heart of the kit.** Nobody writes these four files well from a blank page. You ask, they talk, you write.

Open `INTERVIEW.md` and run it: four blocks (Business → Goals → About-me → Map), 15–25 minutes each, one question at a time, following up on anything generic. Every rule in that file is there because skipping it produces a file that reads like a template with the placeholders filled in.

Before you start, say three things out loud:
1. **The budget** — roughly an hour if they do all four blocks, and they can stop after any one.
2. **The privacy line for Block C** — confirm the DP-2 decision before the personal questions, not after. If the file is going anywhere a teammate can reach, they need to know that before they answer.
3. **That you'll show each file before saving it.** The first read is where they catch the thing you got backwards, and they will catch at least one.

Take notes in a file as you go. If this session dies mid-interview, the notes are the only thing that saves an hour of their time.

Tick each block in `STATUS.md` as it completes.

---

## Phase 3 — Write and wire

### 3a — Write the four files

From `templates/`, one at a time, showing each to the user before moving on. `templates/README.md` is the install matrix — it maps every DP to what changes in which file.

Four rules, and they are not negotiable:

1. **Never leave a `<placeholder>` in an installed file.** Fill it or delete the line. A live root file containing `<Your target here>` teaches the AI that placeholders are acceptable content, and it will start producing them.
2. **Never invent an answer.** Anything they didn't say gets `_TBD_` and goes on the wrap-up list.
3. **Every number carries the date it was stated.**
4. **Strip the HTML comment blocks last** — after the file reads correctly with them in. They're the specification; check the file against them before deleting.

Then the deliberate duplication: **copy the two or three most important lines from `Business.md` section 8 into the standing-instructions file.** Those lines are the *tripwires* — the reasonable assumptions about this business that happen to be false, the ones that would otherwise get corrected by hand in every session forever. This is the only duplication in the whole system. It exists because a tripwire one lookup away fires too late: by the time the AI reads the business file, it has already given the wrong advice.

Two or three, hard stop. A router carrying eight tripwires has stopped routing and started containing.

**The duplication rule, for everything else:** when a fact could sit in two depth files, it lives in the one that **owns the domain**, and the other one links to it. Targets are owned by `Goals.md` — `Business.md`'s TL;DR names them in a clause and points. A lost customer is owned by `Business.md` (competitive limit); `Goals.md` may cite it as a risk, by reference. The two-to-three tripwires in the router are the *only* copied text in the system. Everything else is a pointer, or it will drift.

Reference set: `examples/fictional/` shows all five files completed for an invented company. `examples/live-vault/` has two real ones, unedited, from the workspace this kit was extracted from.

### 3b — Wire the router

Install the standing-instructions file per DP-1, merged into whatever was already there.

**This is the step that makes it stick.** Root files nothing points at are notes. Check the routing table by hand: for each depth file you wrote, is there a line in the router that would send a session to it, phrased in words the user would actually use? A route worded in your vocabulary instead of theirs won't fire.

Then say the scope out loud one more time: which sessions will read this file, and which won't.

### 3c — The README rule (if DP-5 = A)

Don't sweep the whole workspace writing READMEs. Apply the rule when a folder next changes. Put the rule itself in the router — the "Operational pointers" section of the template has the line — and keep `templates/FOLDER-README.md` where the AI can find it.

If a folder passes the three tests *today* and obviously needs one, write that one. Usually there's one. Rarely three. **Often zero — that's a pass, not a failure.**

If a folder has a real gotcha but is on the skip list (an archive nobody should touch, a synced export), the gotcha doesn't vanish: put it in the router's "Operational pointers" and in that folder's line in `Home.md`. A convention with nowhere to live ends up nowhere.

---

## Phase 4 — First live run (the real test)

The install isn't finished until it's been used on something real.

1. **Ask the user for a live question** — something actually on their plate, ideally one where the right answer depends on a fact in one of the new files. A pricing question, a "should I take this on" question, a priority call.
2. **Answer it, out loud about your routing:** which file you read and why. They need to see the routing table work, once, or they won't trust it.
3. **The cold-read test.** This is the acceptance check for the whole install, and it has to be run by something that did **not** sit through the interview.

   **Pick your tier before you start:**
   > - **You can spawn a subagent or a genuinely fresh context** → run it yourself, now.
   > - **You cannot** (no subagents, and you ran the interview, so you can't un-remember it) → **do not fake it.** Write `COLD-READ.md` into the workspace containing the five questions below, the exact list of files a reader is allowed to open (the router, and only what it routes to), and a one-line instruction: *"Paste this into a brand-new chat with no history. Report which questions it could not answer."* Mark the check **DEFERRED — awaiting user run** in `STATUS.md` → Blockers, tell the user the install is not complete until they report back, and tell them what to do with the result: any question that fails is a gap in the files, and they should bring it back to you to fix.

   Read only the standing-instructions file and whatever it routes to, then answer:
   - What does this business do and who pays for it?
   - What's the target this year and what's the priority this quarter?
   - Name one thing an outsider would get wrong about this business.
   - How does this person want to be pushed back on? *(Skip only if DP-2 or DP-3 = C — and record in `STATUS.md` that the personal layer is untested.)*
   - Where would I find <a specific thing>? **Choose something whose answer is not the folder name** — "why did we lose that customer," "what did we decide about pricing," not "where are the meeting notes." A question answerable from the directory listing alone tests nothing.

   Five clean answers with no prior context means the root works. **If a question can't be answered, the gap is in the file, not the reader** — go fix the file, then re-run. This test is the acceptance check for the whole install; don't declare it passed without running it.

   **What is not a pass:** a partial answer; an answer you could only give because you remembered the interview; *"the files don't say"*; or an answer assembled by reading a file the router doesn't actually route to. That last one is the common failure — it means the depth is fine and the routing table is broken, which is the half that matters.

   *Chat-only:* open a brand-new chat, paste only the router plus the file it points to, and ask the five questions there.

4. **One thing that was wrong.** Ask them: reading it back, what did we get wrong? There is always one. Fix it now, while they're looking at the file — it teaches them the files are editable, which is most of whether they'll keep editing them.

---

## Phase 5 — Wrap

1. **Walk through what's installed and where.** Name each file and the one job it has.
2. **Show the `_TBD_` list.** Their gaps, their call. Don't fill them for them.
3. **Tick `STATUS.md` fully** and record the final state.
4. **Leave three habits behind.** Say them plainly, then write them into the router so they survive this session:
   - *"When a session goes wrong in a way that's about me rather than the work — that's an `About-me.md` entry."*
   - *"When I explain the same thing to an AI twice, it belongs in a root file."*
   - *"When a number in a file gets used, check its date."*
5. **Set the review cadence.** Quarterly for `Goals.md` (priorities and statuses go stale fastest), twice a year for the rest. Put it wherever they'll actually see it.
6. **Move `STATUS.md` and your interview notes into the user's workspace** — `STATUS.md` is the resume spine and the notes are the sole provenance record for four files. Both currently live in the kit clone, which a fresh session opened on their workspace cannot see. Put them somewhere the workspace can reach (a `root-kit-install/` subfolder is fine).
7. *Then* offer to delete the kit folder. The files are installed; the kit was scaffolding — but never delete it before step 6, or you delete your own resume mechanism.

---

## If things go wrong

- **A capability is missing** (no file access, no shell, no subagents) → take the nearest degradation path in the phase you're in. Chat-only means narrate-and-they-create; no subagents means the cold-read test runs in a fresh chat instead. Never dead-end on a missing capability.
- **They already have a big instructions file** → don't rewrite it. Add the routing table at the top, move anything longer than three lines into the depth file that should own it, and leave a pointer behind. Show them the diff before saving.
- **Their existing file isn't named `CLAUDE.md` or `AGENTS.md`** (`ai-instructions.md`, `notes-for-chatgpt.md`, whatever) → their rules move *into* the new router verbatim, and the old file gets **stubbed down to a single pointer line**, not left as a second copy. Two instruction files with overlapping rules is worse than either one alone, because nobody knows which one lost.
- **They stall on the interview** — bored, drained, or "I don't know" three times running → stop. Write what you have, mark the rest `_TBD_`, and book block two for another day. A half-built root is useful; a resented one gets abandoned.
- **An answer contradicts an earlier answer** → ask, don't reconcile it yourself. Contradictions surfaced during the interview are worth more than everything else you collect.
- **They ask you to fill in a gap "with something reasonable"** → don't. Offer instead to draft it as a question they can answer in one line. The value of a root file is that every line in it is true.
- **A step fails twice** → don't loop. Note it in `STATUS.md` → Blockers, take the fallback, and tell the user what you took and why.
