<!--
TEMPLATE — a per-folder README.

*** READ THE RULE BEFORE YOU USE THE TEMPLATE. ***

## Does this folder earn a README?

A folder earns one only when at least one is true:

  (a) NAVIGATION HUB — it has multiple subfolders and there's a real routing decision to
      make on arrival.
  (b) NON-OBVIOUS PURPOSE — the folder name alone doesn't tell you what's in here or how
      to use it.
  (c) CONVENTIONS OR GOTCHAS — there are rules, a "never touch X," a naming scheme, or a
      cross-link a newcomer would miss.

SKIP: homogeneous leaf folders. Transcripts, attachments, images, archives, daily notes,
exports — anything where the contents are all the same kind of thing and the folder name
already says which kind.

*** THE GUARD *** — if every section you'd write would just restate the folder name plus a
directory listing, write nothing. An unread README that has gone wrong is worse than no
README: it actively misinforms, and it costs context every time an AI reads it.

## When to update

Trigger: the folder's STRUCTURE, PURPOSE, or CONVENTIONS changed. Not individual file
edits. A README that updates on every file change is a changelog wearing a hat, and it
will be stale anyway.

## The shape

Frontmatter always. Body sections only where they're non-obvious — omit any section that
would restate the folder name. A three-line README is a good README.

Delete every comment block before you install.
-->

---
type: <domain | build | map | archive>
read_first: <README.md | STATUS.md>
updated: <YYYY-MM-DD>
---

# <Folder name>

## Purpose

<!-- One line. What this folder is for. If you need two, one of them is probably a gotcha. -->

<One line.>

## Start here

<!-- Where a newcomer (human or AI) should go first, and why. Omit if the answer is
     obviously "read the files." -->

<The one file to read first.>

## Map

<!-- Subfolder index — one line each. Omit entirely if there are no subfolders, or if
     their names already say everything. This is the section that makes a navigation hub
     worth having. -->

- **`<subfolder>/`** · <what's in it> → <where it routes next>
- **`<subfolder>/`** · <what's in it>

## State

<!-- BUILDS ONLY — a project or piece of work in progress. Where it stands, what's next.
     If the folder is a permanent domain rather than a build, delete this section: state
     that belongs in a STATUS.md doesn't belong in a README. -->

<Current position, dated. Or a pointer to STATUS.md.>

## Gotchas

<!-- Conventions, cross-links, and don'ts a newcomer would otherwise get wrong. This is
     usually the reason the folder earned a README in the first place — if you're writing
     a README and this section is empty, re-read the three tests above. -->

- <convention or don't>
- <cross-link that isn't obvious from here>
