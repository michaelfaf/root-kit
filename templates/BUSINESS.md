<!--
TEMPLATE — BUSINESS.md, the canonical model.

WHAT THIS FILE IS: the single source of truth for how the business actually works — model,
customers, pricing mechanics, edge, expansion, team, and the rules an outsider gets wrong.
Written so an AI that reads only this file gives advice that fits your business instead of
the generic version of your industry.

WHAT IT IS NOT: a business plan, a pitch deck, or a dashboard. No live figures that change
weekly (see the "live numbers" rule below). No aspirations — those are Goals.md.

THE TWO RULES THAT MAKE THIS FILE WORK:
 1. STRUCTURE STAYS, ACTUALS POINT. Pin the mechanics (how you charge, what counts as cost
    of goods, what the tiers are). Point at the system of record for anything that changes
    week to week (this customer's rate, this month's number). A confidently-stated stale
    number is worse than no number.
 2. EVERY CLAIM CARRIES A SOURCE. Bracket the origin — [owner, date], [a named document],
    [the CRM]. Six months from now the only way to know if a line is still true is to know
    where it came from.

Section 8 is the most valuable section in the file. Write it last, when the rest has
reminded you what outsiders keep getting wrong.

Delete every comment block before you install.
-->

---
type: canonical-reference
read_first: Business.md
updated: <YYYY-MM-DD>
---

# Business — <Company>

Canonical source for the model, customers, pricing, and expansion. The standing-instructions file routes every business-model question here. Read the TL;DR in 90 seconds; read in full for detail. Sources cited in brackets — key at the foot.

> **Last verified:** <YYYY-MM-DD> · **Currency check:** <the one thing most likely to have gone stale, and how to tell>.

---

## TL;DR

<!-- Six to eight bullets. If the AI reads nothing else in this file, this is what it must
     get right. Rewrite this every time the file changes materially. -->

- **What:** <what you sell, to whom, where>.
- **Who pays:** <segments, and roughly what share of revenue each is>.
- **How you deliver:** <labor/fulfilment model in one line>.
- **Edge:** <why customers pick you — and if it isn't price, say so>.
- **Targets:** <this year> → <number>. <horizon year> → <number>.
- **Growth lever:** <the one thing that scales — more customers here, new geography, new product>.

---

## 0. Identity & record

| Field | Value |
|---|---|
| Legal entity | <> |
| Trading name / brand | <> |
| Location | <> |
| <Other stable facts a session needs> | <> |

<!-- Stable facts only. No credentials, no account numbers, no anything you'd mind a
     screen-share catching. -->

---

## 1. Business model

<!-- The mechanism. How does money actually flow? Who does the work? What's structural
     (locked, not a phase) vs. what's a current choice you might reverse? Say which. -->

<Two or three paragraphs.>

**<The structural fact that drives everything else>** — <why it's locked, and what it implies>:
- <Implication for cost structure>
- <Implication for scaling>
- <Implication for risk>

### What you sell

**Current scope:** <list>
**Coming:** <list, with what's blocking each>
**Explicitly out of scope:** <list — this is the part that stops the AI proposing work you don't do>

---

## 2. Customers & segments

**Segments:** <each one, one line, with what share of revenue>

**Tiers or classification** <if you have one — the bands, and what each tier *changes* about how you treat them>:

| Tier | <criterion> | What changes |
|---|---|---|
| <> | <> | <> |

> Live rosters and counts live in <system of record>, not here. They shift constantly and would go stale pinned to a file. <Say who fetches: "the AI pulls it" (DP-4=C) or "open <system> → <screen>; the AI can't reach it" (DP-4=D).>

### Lifecycle

<!-- The path from "we get the work" to "we get paid." Number the steps and name the owner
     of each. This section is what lets an AI answer operational questions without asking you. -->

1. <step> → <owner>
2. <step> → <owner>
3. <step> → <owner>

---

## 3. Pricing & margin mechanics

### How you charge

<!-- The MODEL, not the numbers. Per unit / hourly / retainer / project / subscription;
     minimums; what's negotiable and what isn't; whether a standard rate card exists. -->

- <mechanism>
- <mechanism>

> **Live numbers:** each customer's agreed pricing lives in <system of record>. <Who fetches — under DP-4=D write "ask me and I'll pull it from <system>", not "pull it", because the AI can't.> <Why there is no canonical price list here, if there isn't.>

### Margin mechanics

<!-- The section that stops an AI giving you advice built on the wrong cost structure.
     What sits in cost of goods vs. overhead? What's your comparable peer group, and who
     is NOT a valid comparison? What moves margin most? -->

- **<What sits in COGS> vs. <what sits in overhead>.** Don't blur them in any financial read.
- **Benchmark only against <the valid peer group>** — never <the invalid one>. <Why.>
- **Margin history:** <numbers, with dates>.
- **<The lever that actually moves margin>:** <explanation>.

---

## 4. Value proposition & competition

**Throughline:** *<one sentence — the thing you're really selling>*

**The uniques:**
1. <>
2. <>
3. <>

**Positioning:** *"<the line you'd say out loud>"*

**What the claim is NOT:** <the claims you deliberately don't make, and why> — this is as important as the claim itself.

### Competitive landscape

- **<Competitor or category>** — <what they are, whether they're actually a competitor>
- **Known limit:** <the situation where you lose, honestly stated, with the example that taught you>. <What it means for where you compete.>

---

## 5. Geography & expansion

**Current:** <where you operate>
**Growth model:** <how a new market/segment/product actually gets opened — the repeatable steps>
**Seasonality:** <if it applies — the shape of the year and what you do in the trough>

---

## 6. Targets & metrics

<!-- The metrics you steer by and WHO OWNS each. Targets themselves live in Goals.md;
     this table is the instrument panel, not the destination. -->

| Metric | Owner | Why it's tracked |
|---|---|---|
| <> | <> | <> |

---

## 7. Team & structure

Full detail: <pointer to a people file, if you have one>. This is a pointer, not a replacement.

- **<Name/role>** — <what they own> · <what they can decide alone> · <what needs you> · <COGS or overhead>
- **<Name/role>** — <same>

---

## 8. Rules that must not be gotten wrong

<!--
*** THE MOST VALUABLE SECTION IN THIS FILE. ***

These are the tripwires: the things a smart outsider would reasonably assume that are
false in your business. Every one of them is a piece of advice you'd otherwise have to
correct by hand, in every session, forever.

Find them by asking: what did the last consultant/advisor/AI get wrong about us?
What do I find myself explaining more than once a month?

The two or three most important also get copied up into the standing-instructions file —
compressed to one line each, not pasted whole; see the fictional example. They must be
true in every session without this file being read. That is the only duplication in the
whole system, and it's deliberate.
-->

- **<Rule>:** <the assumption, and the correction>.
- **<Rule>:** <same>.
- **<Structural non-negotiable>:** <what it is and why it's not a preference>.

---

## 9. Discontinued / pivots

<!-- What you tried and stopped, and why. This section exists for one reason: to stop the
     AI enthusiastically proposing the thing you already killed. Include the reasoning,
     not just the decision — reasoning is what makes it re-usable judgment. -->

**<Thing> — discontinued <date>.** <Why. What replaced it. Whether it's permanent.>

---

## Source key

| Cited as | Source |
|---|---|
| <> | <> |
| <Owner, date> | Direct input |
