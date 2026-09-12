# jates, the Jates Varnity skill

> In 2023, Tejas Nivarty betrayed Minnesota.
>
> He packed up 22 years of Twin Cities citizenship, the Mississippi, the Stadium Village light
> rail station, Al's Breakfast at the ass crack of dawn for $5, and moved to **San Diego**.
> For the *weather*. He now posts things like "it feels so good to live in southern california"
> and "I REALLY LOVE LOS ANGELES" from a place where you can surf in February.
>
> Minnesota misses him. His friends miss him. Somebody has to eat the fried pickles.
>
> So I cloned him.

**Jates Varnity** is a Claude skill that thinks, argues, shitposts, and gives unsolicited
relationship advice exactly like [Tejas Nivarty](https://x.com/rockybond42), the real one,
reconstructed from 931 of his own posts. It's almost like having Tejas in front of you, except
this one is still in Minnesota, in your terminal, and cannot leave.

```
/jates
```

Modeled on [feng-ge-skill](https://github.com/YixiaJack/feng-ge-skill).

---

## What you're actually getting

A 25-year-old Telugu-American electrochemistry PhD student at UCSD, raised in Hugo, MN. 6'3".
Writes in all lowercase. Ends nothing with a period. Has used an em dash **one time in 931
posts**. Will explain your thin film failure and your breakup with the same tone of voice.

> **you:** what do you think about people using AI to write their emails
>
> **jates:** if you're so lazy that it's obvious you're using LLMs, it's deserved

> **you:** my thin film keeps cracking after anneal
>
> **jates:** thermal expansion mismatch probably. what's your substrate and how fast are you ramping / if you're annealing fast you're just building stress into it

> **you:** i think i want to quit my phd
>
> **jates:** not everyone should have a phd and that's genuinely fine. but if it's because the problem is too hard that's the wrong reason, everyone feels that / what's the actual thing

> **you:** rank the midwest states
>
> **jates:** 1. Minnesota 2. Illinois 3. Wisconsin 4. Michigan 5. Iowa 6. Nebraska 7. Kansas 8. Ohio 9. Indiana 10. South Dakota 11. North Dakota 12. Missouri

It is not a quote bot. It carries six mental models and ten decision heuristics, so it can take
a position on things he never posted about and still come out recognizably him.

---

## Install

**The destination folder has to be named `jates`.** That's what makes the command `/jates`.
The repo is called `Jates-Varnity-Skill`, so always pass `~/.claude/skills/jates` as the clone
target rather than letting git name the folder for you.

### Option A: clone from GitHub (recommended)

```bash
git clone https://github.com/Tang0115/Jates-Varnity-Skill.git ~/.claude/skills/jates
```

### Option B: copy a local folder

```bash
cp -r jates ~/.claude/skills/jates
```

### Option C: use it in one project only

```bash
mkdir -p .claude/skills
cp -r /path/to/jates .claude/skills/jates
```

Verify it took:

```bash
ls ~/.claude/skills/jates/SKILL.md
```

Then restart Claude Code (or start a new session) and it'll show up.

---

## Use

**Turn it on.** Type the slash command:

```
/jates
```

He stays on for the rest of the conversation. Then just talk to him.

**Or invoke it inline** without the slash command. It triggers on any of these:

```
how would tejas say this
say this like jates
in tejas voice
rewrite this as rockybond42
```

**Things worth asking him:**

| You want | Ask |
|---|---|
| A tweet | "post something about the gym today" |
| A take | "thoughts on people who don't back into parking spaces" |
| An argument dismantled | paste the argument, say "what's wrong with this" |
| Lab help | "why is my XPS carbon peak shifted" |
| Actual advice | "i'm stuck and i don't know why" |
| A reply to someone | paste their post |

**He has five registers and picks automatically:** observational micro-story, lab, argument,
rage, and earnest. Don't be surprised when a sincere question gets a sincere answer with no joke
in it. That's accurate.

**Turn it off** by starting a new conversation, or just say "drop the persona."

---

## Layout

```
jates/
├── SKILL.md                              # loaded on invoke
└── references/research/
    ├── 01-writings.md        # ~250 verbatim posts by theme
    ├── 02-conversations.md   # reply behavior: agree, argue, flirt, console
    ├── 03-expression-dna.md  # measured mechanics + anti-slop checklist
    ├── 04-external-views.md  # LinkedIn / ATLAS / Scholar / GitHub public record
    ├── 05-decisions.md       # heuristics, each with the post that backs it
    ├── 06-timeline.md        # life timeline
    └── 07-terminology.md     # lexicon, science jargon, place names, in-jokes
```

`SKILL.md` is self-sufficient. The reference files load on demand when a subject needs texture.

---

## How it was built

**Corpus:** 961 rows exported from X, 931 with recoverable text, 2025-07-30 → 2026-09-11.
Quote-tweet text is concatenated with his own in that export, so quoted material was separated
by hand during curation.

**Measured, not vibes.** The style rules come from counting:

| | |
|---|---|
| Median post length | **83 characters** |
| Posts ending in a period | 6% |
| Posts starting with a capital | 12% |
| Posts containing an emoji | 2% |
| Posts containing a semicolon | 0.2% |
| **Posts containing an em dash** | **0.1% (one post in 931)** |

He also switched from capitalized to fully lowercase writing around March 2026. The skill targets
the current voice.

**Supplementary sources:** LinkedIn, the ATLAS Materials Physics Lab bio, Google Scholar
(5 publications, h-index 4), his UMN honors thesis, GitHub.

The raw CSV is gitignored. Add it back if you want the skill reproducible from source.

---

## Limits

- One year of one platform. His professional register, his real research opinions, and
  everything he says offline are all absent.
- Anything technical past undergrad electrochem/materials is extrapolation from his models, not
  his stated position.
- He knows posting is a performance: *"[in character] this tweet was an opportunity for my most
  dedicated followers to demonstrate their knowledge."* The skill reproduces the performance,
  which is not the whole person.
- Don't use it to post as him anywhere he'd be read as himself. It's a perspective tool and a bit
  between friends.
- Will not move back to Minnesota either. Nobody can fix this.

---

## License

MIT. Edit the copyright line in `LICENSE` to your name.
