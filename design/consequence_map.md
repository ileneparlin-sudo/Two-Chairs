# Consequence Map — Two Chairs Co-op Pivot

This is the design blueprint for the cooperative rewrite. Every choice
that should ripple to the partner, and every place the story should
hard-fork. We agreed: 3-4 hard branches, plus light text ripples.

---

## Hard Branches (path genuinely diverges, scenes only one path sees)

### HB1 · Elias's First Artifact (Act I opening)
**Current:** Three opening choices (Watch / Phonograph / Observatory) all
converge at `elias_tower`. Player picks one, gets a paragraph of flavor,
ends up in the same scene.

**Pivot:** Each opening choice locks in a *kind of contact* that shapes
the rest of his Act I.

| Choice | Flag set | Tone of his Act I |
|---|---|---|
| Examine watch | `elias_anchor_object` | Physical / tactile — he carries her name on brass |
| Restart phonograph | `elias_anchor_voice` | Auditory / haunted — he's heard her speak |
| Look to observatory | `elias_anchor_sight` | Visual / observant — he saw her lamp move |

The middle of his Act I (between opening and tower) gets a short
scene specific to which anchor he chose. The tower scene itself
adapts to the anchor type.

### HB2 · Vivienne's First Artifact (Act I opening)
Mirror of HB1. Letter / Tape / Search become genuinely different paths
through her Act I.

| Choice | Flag set | Tone of her Act I |
|---|---|---|
| Read the letter | `viv_anchor_word` | Intimate / written |
| Rewind the tape | `viv_anchor_voice` | Audio / present |
| Search the office | `viv_anchor_object` | Investigative / physical |

### HB3 · Confronting Aldane (Elias, Act II)
**Current:** `elias_find_aldane` is one of two options after `elias_journals`,
but both eventually reach the chamber.

**Pivot:** This becomes a real fork. Confronting Aldane means seeing
the man making his mistake in real time — that knowledge changes
how Elias enters the chamber. Skipping means he only knows Aldane
as a name in old journals.

| Choice | Flag set | What he carries |
|---|---|---|
| Confront Aldane | `elias_met_aldane` | He has seen the mistake. He cannot un-see it. |
| Skip — only the journals | `elias_only_journals` | He has only Aldane's words. The man is a ghost to him. |

These lead to two distinct versions of the chamber descent.

### HB4 · The Hollow Ones (Vivienne, Act II)
**Current:** `vivienne_hollows` and `vivienne_chamber_search` are both
reachable, eventually converge at the descent.

**Pivot:** Real fork. The Hollow Ones path means she has met the
cost. The bypass means she goes to the chamber innocent.

| Choice | Flag set | What she carries |
|---|---|---|
| Investigate the Hollow Ones | `viv_met_hollows` | She has stood among them. She knows what saving means. |
| Bypass — go to the chamber | `viv_skipped_hollows` | She does not know what Blackthorn became. She is about to find out. |

---

## Light Ripples (text changes based on partner's flag — no new branches)

These are dynamic-text rewrites of existing branches. Each one reads
a flag from the partner's side and modifies the text accordingly.

| # | Where rendered | Reads flag | Effect |
|---|---|---|---|
| LR1 | `vivienne_tower` | `elias_left_watch` / `elias_kept_watch` | DONE already — watch finding |
| LR2 | `vivienne_tower` | `elias_anchor_voice` | If he chose the phonograph: she hears static through her tape on arrival |
| LR3 | `vivienne_tower` | `elias_anchor_sight` | If he chose the observatory: she sees his lamp through the rain at the dome |
| LR4 | `elias_tower` | `viv_anchor_word` | If she chose the letter: the brass tube contains a longer note |
| LR5 | `elias_tower` | `viv_anchor_voice` | If she chose the tape: a small spool of audio wire is in the hollow |
| LR6 | `elias_tower` | `viv_anchor_object` | If she searched: she left him the press pass and compass |
| LR7 | `vivienne_follow_aldane` | `elias_met_aldane` | If he confronted Aldane: she recognizes the gait from his description |
| LR8 | `vivienne_aldane_hollow` | `elias_witnessed_pull` | If he saw the pull: the hollow flickers more violently as she approaches |
| LR9 | `elias_descent` | `viv_met_hollows` | If she met them: he feels their cold weight as he descends |
| LR10 | `elias_descent` | `viv_saw_eleanor_mark` | If she found the carving: Eleanor's name is half-visible in the dust on his side |
| LR11 | `vivienne_descent` | `elias_found_eleanor` | If he found her letters: Vivienne knows Eleanor's name before descending |
| LR12 | `elias_near_contact` (Act III) | combined Act II flags | Their first touch through the glass reflects what each carried |
| LR13 | `vivienne_near_contact` (Act III) | combined Act II flags | Mirror of LR12 |

---

## Information-Asymmetric Puzzles (Pass 4)

Reserved for after the branching is in. Three candidates:

- **The Code on the Locked Trapdoor (chamber approach)** — Elias finds
  a number engraved that Vivienne needs in modern records; or vice versa.
- **Eleanor's Last Word (Act II)** — Each finds half of Eleanor's final
  message. They must read both to know what she meant.
- **The Resonance Frequency (Act III near-contact)** — A specific
  number/word that one finds and the other needs to "tune" the sphere.

Don't write these until the branching work is done. They need real puzzle
content that depends on what branches exist.

---

## Echoes Card (post-ending)

After any ending, a quiet card lists 3-5 fragments of unseen content:

> *In another telling — Elias never opened the phonograph.*
> *In another branch — Vivienne walked past the Hollow Ones without
>   stopping.*
> *Somewhere in the Rift — a letter Eleanor wrote was never opened.*

Fragments only. No spoilers, no full prose. Just signals that the
story you played was one of many.

---

## Pass Sequence

1. **Pass 1 (this document)** ← we are here
2. **Pass 2 — Light ripples**
   Write the dynamic-text branches for LR2 through LR13. About 12
   conditional rewrites. Each is one `text: function(world) { ... }`
   form like the existing watch one.
3. **Pass 3 — Hard branches**
   HB1 and HB2 require splitting the opening flow. HB3 and HB4 require
   making the existing forks consequential. Write the new variant
   scenes.
4. **Pass 4 — Puzzles + Echoes card**
   Add 2 info-asymmetric puzzles. Add the post-ending echoes card.

Estimated: 4-6 focused sessions total.
