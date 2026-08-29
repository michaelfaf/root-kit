# Overview — what this is and why it works

Read this before you install anything. It's the *what* and the *why*; `IMPLEMENT.md` is the *how*. About ten minutes.

---

## The problem

You've been using an AI assistant for a while. It's good at the task in front of it and useless at everything around it. Every session you re-explain the same things: what your business actually does, who pays you, what you're trying to hit this year, why the obvious advice doesn't apply to you. You correct the same wrong assumption for the fortieth time.

So you write it down. A big instructions file — CLAUDE.md, AGENTS.md, the custom-instructions box, whatever your tool reads. And it helps, for about a month. Then it's 4,000 words, it gets loaded into every single session including the one where you asked it to rename a variable, and it *still* doesn't have the section you needed, because the sections you need are the deep ones and deep sections are exactly what won't fit in a file that's read on every turn.

That's the trap. The file that's always loaded has to be short. The context you actually need is long. Both are true and they can't be the same file.

## The idea

**Split them.** The always-loaded file stops holding the depth and starts *routing* to it.

It keeps the things that must be true on every turn — who you are, how to talk to you, what to never get wrong, what needs your sign-off — and adds a table that says, in your own words, which question goes to which file:

```
Coaching, behavioral, "am I being an idiot about this"  →  About-me.md
Targets, priorities, what matters this quarter          →  Goals.md
Business model, customers, pricing                      →  Business.md
Where anything lives                                    →  Home.md
```

Now the depth can be as deep as it needs to be, because nobody pays for it until it's needed. And your always-loaded file goes back to being short enough that nobody minds it loading every turn.

The thing that makes this work rather than just being tidy: **an AI reads a route.** It's not searching your notes and half-finding something. It's told, in a file it always has, that pricing questions live in a specific file. So the right file gets read on the right turn, and each fact has exactly one home.

## What you end up with

Five files at the root of wherever you work.

**The router** — `CLAUDE.md` or `AGENTS.md`, depending on your tools. The routing table, plus your identity, your rules and boundaries, how you want decisions handed to you, and the two or three business facts that must be true in every session. Deliberately small — it routes instead of containing (the template states the target).

**`Home.md`** — the map. Top-level folders and load-bearing files, one line each, every entry routing onward. Never leaf notes. This is *where things are*, not how they work.

**`Business.md`** — the canonical model. What you sell and to whom, how you charge, what sits in cost of goods versus overhead, why customers pick you, where you lose, what you've stopped doing and why. Its most valuable section is the one titled **"rules that must not be gotten wrong"** — the things a smart outsider would reasonably assume that are false in your business. Every entry there is a piece of bad advice you'd otherwise correct by hand forever.

**`Goals.md`** — target state. This year's number, the countable goal underneath it, this quarter's priorities with owners and binary done-lines, the cadence that has to hold no matter what, and the risks. Not a progress log — that's the single most common way this file rots.

**`About-me.md`** — the person. Purpose, strengths, blind spots, decision style, where you need concepts explained before advice. Its most valuable section is **"how to push back on me,"** because that section is an instruction, not context. Read on demand, not every session.

Plus **the README rule**: a folder earns a README only when it's a navigation hub, its purpose isn't obvious from the name, or it carries conventions someone would otherwise get wrong. Everything else gets nothing, deliberately.

## The concepts, defined

**Standing instructions** — the file your AI tool reads automatically at the start of every session. Different tools read different filenames (`CLAUDE.md`, `AGENTS.md`, a custom-instructions box) and at different scopes. The kit finds out which one yours reads before writing anything.

**Router vs. depth** — the split this whole system rests on. The router is always loaded and stays small; depth files are read on demand and can be long. A fact belongs in the router only if it must be true on every turn.

**Depth file** — a root file the router points at. Four of them, one per domain.

**Routing table** — the lines in the router mapping an intent to a file. Written in the words *you'd* use, not the AI's, or it won't fire on a real question.

**Tripwire** — a fact in "rules that must not be gotten wrong." Not a summary of the business; specifically the reasonable assumption that's false here. *"Our subcontractors sit in cost of goods, not payroll — don't benchmark us against companies with in-house crews"* is a tripwire. It changes every margin conversation you'll ever have.

**Gate** — a named check in `About-me.md` that fires on a trigger. A blind spot written in a file is a fact the AI knows and never acts on. A gate is the same blind spot with a trigger and three questions attached, and it changes behavior. This is the highest-value thing in the personal file, and it's usually written a week after the thing it would have prevented.

**Pin vs. point** — how numbers are handled. Structural facts get *pinned* in the file with a date. Live figures get *pointed at* — the file names the system of record and the AI pulls from it. A stale number stated confidently is worse than no number.

**Cold-read test** — the acceptance check. A fresh session with no history reads only the router and what it points at, then answers five questions about your business, your targets, and you. Five clean answers means the root works. Anything it can't answer is a gap in the file, not in the reader.

## How the install actually goes

**Scan.** Your AI works out what it is, which instructions file your platform reads and at what scope, where your work lives, and what's already at the root. It reads any existing instructions in full — it's merging into your conventions, not replacing them.

**Seven decisions.** Which file the router goes in. One workspace or personal split from shared. How much of the personal file to write now. Numbers in-file or pointers. README depth. Obsidian-native or plain markdown. Whether to restructure your folders (the recommendation is no — this kit deliberately doesn't impose a folder scheme). Each comes with trade-offs and a recommendation, and each gets recorded.

**The interview.** This is the heart of it and it's most of the hour. Your AI asks and you talk — five blocks, business first, the personal one third, the map and a short working-together block last. Nobody writes these files well from a blank page; the reason this works is that answering good questions is much easier than filling in a template. Some of the questions are ones nobody has asked you: *what are the three things an outsider gets wrong about your business that would make their advice useless?* *What decision from the last year would you take back, and what pattern caused it?* *How do you want to be pushed back on — before you've decided, or after?*

**Writing and wiring.** Your AI writes the four files from your answers, showing you each one before it moves on. Then it installs the router and checks the routing table line by line against the files that now exist. Nothing invented; anything you didn't say gets marked `_TBD_` and shown to you at the end.

**The live test.** A real question of yours, answered with the routing narrated out loud. Then the cold-read test — which has to be run by something that didn't sit through your interview. An AI that can spawn a fresh session runs it immediately; one that can't will write you a short `COLD-READ.md`, ask you to run it in a new chat or session, and leave the install marked incomplete until you report back. Either way the test is the acceptance check, and a failure means a file needs fixing, not that you did it wrong. Then one more question: *reading it back, what did we get wrong?* There's always one, and fixing it in front of you is how you learn the files are editable.

## Your job vs. your AI's

**Yours:** answer honestly, especially the uncomfortable questions. Make the seven decisions. Read each file when it's shown to you and say what's wrong. Then keep the habit: when you explain something to an AI twice, it belongs in a root file.

**Your AI's:** scan, present decisions with a lean, run the interview, write the files in your words, wire the router, prove it works, and never invent an answer.

## What you need

Any AI that can read and write files handles the whole thing. Claude Code, Codex, Cursor, Cline, Copilot — all fine. Obsidian is nice and not required; the files are plain markdown. A chat-only assistant works too, with more typing: it narrates, you create the files, and you keep the progress checklist yourself.

No subscriptions, no accounts, no software. It's five markdown files and a habit.

## What this is not

**Not a note-taking system.** It doesn't tell you how to organize your notes, and it deliberately doesn't install a folder scheme. It's the root layer that sits *above* whatever you already have.

**Not a prompt library.** No clever phrasings. It's context, structured so the right piece arrives on the right turn.

**Not tied to a vendor.** Plain markdown, and DP-1 exists specifically so switching tools next year costs you one filename.

**Not finished when it's installed.** `About-me.md` in particular is supposed to start thin and thicken over months, one entry per moment where a session went wrong in a way that was about you rather than the work.

## Where it came from

This is extracted from a working setup: an Obsidian vault run daily with Claude Code by the owner of a small B2B services business, in continuous use and revision for months. The root files in `examples/live-vault/` are that vault's actual router and map, unedited.

What's been generalized: the business specifics, the folder scheme, the vendor choices. What survived is the mechanism — the router/depth split, the four files and what each one owns, the tripwire section, the pin-vs-point rule for numbers, and the README rule.

One thing was *added* rather than extracted: the interview. The original files were written by hand, badly at first, over about a year. The interview is the attempt to get you to the same place in an hour, and it's the part of this kit most worth your attention.
