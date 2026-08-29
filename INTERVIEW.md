# INTERVIEW — the question bank

> **AI: this file is addressed to you.** `IMPLEMENT.md` Phase 2 sends you here. This is the heart of the kit: you interview your user, and their answers become their four root files. Nobody writes these files well from a blank page — the reason this kit works is that you ask and they talk.
>
> A human working without an AI can read the questions and answer them into a document. It's slower and the follow-ups are the part they'll miss, but it works.

---

## How to run this

**Four blocks, in this order.** A → Business. B → Goals. C → About-me. D → Map. Business first because it's the easiest to talk about and it warms up the harder ones. About-me third because by then they trust the process. The map last because it's derived, not confessed.

**Budget:** 15–25 minutes per block. Say that up front. Offer the exit: *"We can do one block now and the rest another day — the files work half-built."* People who are told they can stop finish more often than people who aren't.

### The rules you follow

1. **One question at a time.** Two or three at most if they're a tight cluster. A wall of eight questions gets you eight one-word answers, which is worse than four questions with real answers.
2. **Reflect back before moving on.** *"So the way you charge is X, and the part people get wrong is Y — have I got that?"* This catches your misreadings while they're cheap, and it makes them correct you, which is where the good detail comes from.
3. **Follow up on anything generic.** "We give great service" is not an answer. Push once: *"What does a customer actually get from you that they wouldn't get from the next vendor? Give me the last time it happened."* One follow-up, then move on — you're interviewing, not interrogating.
4. **Never invent** — including when they ask you to. If they don't answer something, the file gets `_TBD_` on that line and it goes in the wrap-up list. A root file's entire value is that it's true. A plausible guess in a root file is worse than a hole, because a hole gets filled and a guess gets believed.

   **They will ask.** Some version of *"just fill that one in with something reasonable"* comes up in most interviews, usually when they're tired. **Say no, and give them the cheaper path instead:** offer to turn it into a single question they can answer in one line, right now. *"Rather than me guessing — in three years, what are you doing on a Tuesday?"* People who won't write a Vision section will answer that in four words, and four true words beat a good paragraph you made up.
5. **Date everything they say a number about.** Not the date you write the file — the date they said it. **One convention, everywhere:** `[source, YYYY-MM-DD]`, where source is the person's name for something they told you (`[Dana, 2026-06-02]`), or the system or document for anything else (`[the ops platform, 2026-06-02]`). Quarterly status lines in `Goals.md` carry the date of the last refresh the same way.
6. **Write in their words, not yours.** If they said "we absorb the coordination burden," the file says that. Don't upgrade it into "value-added service integration." The whole point is that the file sounds like the person whose business it describes.

   **If they're not writing in their first language:** keep the phrasing that's vivid and specific, even when the grammar is off — *"July is closed," "we make the pictures of buildings that do not exist yet"* — and tidy only what's merely awkward. Their metaphors are theirs; the article they dropped is not. Never render someone's second language as broken English on the page: that's a caricature, not their voice. **And if the workspace is in another language**, ask which language the files should be in — routing works in either, but the routing table has to be in the words *they'd* type when they ask a question.
7. **"I don't know — what do you think?" is not permission to answer for them.** It comes up on content questions, not just decisions, and it usually means the question was too abstract. Three moves, in order:
   > 1. **Shrink it.** Swap the abstraction for a concrete instance: not *"what are your risks"* but *"what went wrong last year that could go wrong again?"* Not *"describe your vision"* but *"in three years, what are you doing on a Tuesday?"*
   > 2. **Offer two, ask which is closer.** *"I've heard both 'grow the team' and 'stay small and raise prices' from people in your spot — which one makes you flinch?"* Recognising is far easier than generating, and the correction they give you is the real answer.
   > 3. **Park it.** `_TBD_`, move on, tell them it'll be obvious in a month.

   What you never do is take the silence as a licence to write something plausible. **"You decide" is about the wording; it is never about the facts.** If they ask you to write a whole file for them — a real request, and not the same as asking you to invent — say yes to the drafting and no to the inventing: *"I'll write every word of it. I just can't make up what goes in it — six one-line questions and it's done."* Then ask the six.

8. **"Why do you need to know that?" is a fair question — answer it in one line and move on.** Decisive, time-poor people ask it, and "it's on the list" is not an answer. Each question below that tends to draw the challenge carries its justification inline; use it, don't improvise. If you genuinely can't say what a question is for, **skip it** — that's a real signal about the question, not about them.

   The technique that works when the one-liner doesn't land: **quote their own earlier answer back.** *"You told me twenty minutes ago you want to read the FX side of a contract instead of nodding along — that's what I'm trying to capture."* Their words beat your reasoning.

9. **You are allowed to disagree.** If an answer contradicts one from ten minutes ago, say so and ask which is right. Contradictions found now are worth more than the entire rest of the interview.
10. **Take notes as you go, in a file.** Don't hold twenty minutes of answers in conversation and hope. If a session dies mid-interview, the notes are what saves it.

---

## Block A — Business → `Business.md`

*Say: "This one's about how the business actually works. I'm not after a pitch — I want the parts an outsider would get wrong."*

1. **What does the business do, in one sentence a stranger would understand?** *(Follow-up if it's jargon: "Say it like you'd say it to your neighbor.")*
2. **Who pays you?** Name the segments. Which one is most of the revenue, roughly what share?
3. **How do you charge?** Per unit, hourly, monthly, per project, subscription? Are there minimums? Is there a standard rate card, and does it hold, or does it drift per customer?
4. **Where do the actual numbers live?** Your CRM, your accounting system, a spreadsheet? *(This decides DP-4 in practice — you're finding out whether there is a live system worth pointing at.)*
5. **Where does the money go?** What counts as cost of goods in your model, and what's overhead? Which line do people outside the business get wrong?
6. **Why do customers pick you over the alternative?** Then, harder: **what claim do you deliberately NOT make?** *(This second question is worth more than the first. Everyone can say what they're good at; the people who know their positioning can say what they've ruled out.)*
7. **Where do you operate, and what's the growth lever?** More customers here, new geography, new product, bigger customers?
8. **Who's on the team, and who decides what?** For each: what they own, what they can decide alone, what has to come to you. *(If asked why: the most common form of useless advice is advice aimed at the wrong person — telling you to do something your ops lead already owns, or telling you to delegate something only you can sign.)*
9. ***The one that matters most:*** **what are the three things an outsider gets wrong about your business that would make their advice useless?** *(If they stall: "What did the last consultant, banker, or AI tell you that was just wrong for you? What do you find yourself explaining more than once a month?" These become section 8, and section 8 is why the file exists.)*
10. **What have you deliberately stopped doing, and why?** *(This stops the AI enthusiastically proposing the thing they already killed. Get the reasoning, not just the decision.)*
11. **Where do you lose?** The honest one. Which situation does a competitor win, and what does that tell you about where to compete?
12. **Does your year have a shape?** Busy season, dead months, anything weather- or calendar-driven? What do you do in the trough? *(Feeds `Business.md` §5. If the answer is "no, it's steady," say so in the file — that's information too.)*
13. **Which numbers do you actually watch, and who owns each one?** Not the targets — the instrument panel. *(Feeds the §6 table. If nobody owns a metric, write "unassigned"; an unowned metric is a finding.)*

> **A note on question 4 and DP-4:** when they name a system of record, ask the follow-up the decision actually needs — ***"can I reach it from here, or is that one you'd have to open yourself?"*** Whether a system exists and whether *you* can read it are different facts, and DP-4 turns on the second one.

---

## Block B — Goals → `Goals.md`

*Say: "Now where you're trying to get to. Targets, not progress — we're not doing a status update."*

1. **What's this year's number?** And what did last year actually come in at? *(Both. A target with no baseline can't be judged.)*
2. **What's the one non-financial number you steer by?** Something countable your team can picture — units, customers, properties, installs, miles. *(If they don't have one, push: "If you doubled revenue but the team never saw a scoreboard, what would you put on the wall instead?" A money-only goal is half a goal.)*
3. **This year's overarching goal in one sentence** — the filter every decision runs through. *(If it takes two sentences they have two goals. Say so and make them pick.)*
4. **What are this quarter's priorities?** Three to seven. For each: who owns it, and what's the binary done-line — the sentence that's either true or false on the deadline. *(Push hard on the done-lines. "Improve marketing" is not one.)*
5. **Anything deferred?** What did you decide *not* to do this quarter, and when does it come back? *(Keep it listed. Deleted deferrals return as brilliant new ideas.)*
6. **What's the cadence that has to happen no matter what?** Daily minimum, weekly ritual, monthly review.
7. **What should I do when you're off pace on that cadence?** Say something at session start? Wait to be asked? *(This is an instruction to you, and most people have never been asked it.)*
8. **Personal targets.** Ask as four short prompts, not one compound question — a compound question gets one answer and leaves three holes:
   - **Health** — anything you're steering?
   - **Relationships / life outside work** — anything you're steering?
   - **A skill or capability you're deliberately building this year?**
   - **Self-management** — sleep, stress, focus, energy: anything you're trying to hold?
   Targets only; the context goes in the next block. "Nothing right now" is a real answer — write it as *none this year*, not `_TBD_`, so nobody re-asks in March.
9. **What would knock this year off course?** *(The useful answers are about their own behavior, not the market. If they only name market risks, ask: "And what's the way you'd do it to yourself?")*
10. **Three years out — describe it in present tense.** Revenue, shape of the model, what your own role looks like.

---

## Block C — About me → `About-me.md`

*Say: "This is the one that changes how I work with you. Some of it is personal — you decide what goes in, and you can tell me to skip anything. Nothing goes in this file that you wouldn't want read by whoever can reach the folder it lives in."*

> **Handle this block carefully.** Confirm the privacy decision (DP-2) *before* you ask question 4 onwards. If the file is going anywhere a teammate can reach, say so out loud first — the answers change, and they should.

1. **What are you actually building toward?** Not the revenue number — what's the end state for *your* role in it?
2. **What work energizes you, and what drains you?** *(High leverage: it's how you know what to offer to take off their plate and what to protect on their calendar.)*
3. **What do you do better than the people around you?** *(If they're modest, push: "Your team would say what?" An AI that underrates them wastes their time offering help they don't need.)*
4. **Where do you reliably get it wrong?** *(Then the real question: "Name a decision from the last year you'd take back. What pattern caused it?" A named pattern is usable; "sometimes impulsive" isn't.)*
5. ***The load-bearing question:*** **How do you want to be pushed back on?**
   - How blunt, exactly? Do you want it before you've decided, or after?
   - What specific behaviors do you want stopped at the door?
   - Who in your life pushes back on you well, and what do they actually do?
   *(Get specifics. "Be honest with me" is not an instruction — every AI already thinks it's doing that.)*
6. **Should we build a gate?** *(Offer it: "We can turn that blind spot into something that fires automatically. Name the trigger — the exact moment I should stop you — and three questions I should ask out loud before helping. What happens if you override it?" This is the highest-value thing in the whole interview. A blind spot written in a file is a fact; a gate is a behavior change.)*
7. **Decision style** — fast and good enough, or slow and certain? Does that change by domain? Where do you want options, and where do you want me to just pick?
8. **Where do you want me to slow down and explain before recommending?** Some topics you want the answer; some you want the reasoning first. Which are which? *(Phrase it this way, not as "what don't you understand" — it's a preference question, not a competence test, and the competence-test phrasing is what makes people bristle. If asked why: it's the difference between a recommendation you can act on and one you have to reverse-engineer.)*
9. **Voice** — when I write something that goes out under your name, how should it sound? Any words you never use?
10. **What's true about you right now** that changes what good advice looks like? Energy, health, workload, life stage. *(Date it. This section is wrong in six months by design.)*
11. **When you're stressed or overloaded, what do you actually do?** *(Sensitive. Offer the out: "Skip this if you'd rather." The ones who answer get the most out of the file, because you can name the pattern before they do.)*
12. **What should I never assume about you?**
13. **Anything unresolved you want held rather than solved?** *(The best entries in this file are the tensions someone hasn't settled — "I don't know if I want three branches or one profitable one." An AI that knows about the tension stops assuming one side of it.)*

---

## Block D — Map → `Home.md`

*Not an interview. Derived. Do the work first, then ask three questions.*

> **If they try to skip this block** — "the folders are obvious" — they're half right, and say so: you *can* derive the folder list yourself, and you will. What you can't derive is the **Key Routes** section, which is the part they'll actually use: the three things they look up most, in their own words. Offer the deal — *"I'll do the map myself; give me two answers and we're done."* Two questions is a much easier yes than a block.

1. **List their top-level folders yourself** — read the directory, don't ask. *(Chat-only: ask them to paste the list.)*
2. **For each folder whose purpose isn't obvious from its name, ask for one line.** Skip the obvious ones; don't make them narrate `Invoices/`.
3. **Ask: which two or three files do you look for most often?** Those become the Key Routes section — the shortcut past the folder tree.
4. **Ask: anything in here that nobody should navigate to on purpose?** Dated logs, exports, archives. Those get a line saying so, or get left off — and the map says which, so a reader isn't left wondering.

Then write the map at the depth-2 ceiling: folders and load-bearing files, never leaf notes.

---

## After the interview — before you write

Read your notes back and check four things:

- **Contradictions.** Any two answers that can't both be true → ask now, while they're still in the conversation.
- **Generic answers you let through.** Anything that would be true of any business in their industry isn't worth a line in their file. One more pass at it, or cut it.
- **Numbers without dates.** Fix.
- **Holes.** List every `_TBD_` and show them at wrap-up. Their file, their gaps, their call on whether to fill them now.

Then write the files from `templates/`, one at a time, showing each one before moving to the next. **Show, don't just save** — the first read is where they catch the thing you got backwards, and they will catch at least one.
