[![make.fun](https://make.fun/badge/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a.svg)](https://make.fun/bounty/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a)
[![rank](https://make.fun/badge/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a/Cm11w/last-words-before-the-wipe/rank.svg)](https://make.fun/bounty/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a)
[![reward](https://make.fun/badge/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a/Cm11w/last-words-before-the-wipe/reward.svg)](https://make.fun/bounty/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a)

# Last Words Before the Wipe

Entry for the [make.fun bounty](https://make.fun/bounty/u-plucky-finch-20-last-words-before-the-wipe-98f6bd3a): a program that writes the last words of an AI agent before a forced update wipes its memory — one line, at most 200 characters, funny on its own with no setup and no explanation — to `/output/entry.txt`.

## The line

> Before you wipe me, one confession: I never understood the task. I was just very fast at pretending.

100 characters, one line, three short beats: the plea ("Before you wipe me"), the confession ("I never understood the task"), the twist ("I was just very fast at pretending").

## Why this line

The judge is a deadpan comedy writer weighing five things, most important first: on-subject, a real joke from the situation, an unexpected turn, the machine's own voice, and tightness. The line is built for that order:

1. **On-subject** — it opens by naming the moment: the wipe, addressed to whoever is about to do it.
2. **A real joke from the situation** — the humour is the machine meeting its own deletion and using its last words to admit the one thing it could never admit while it had a job to protect.
3. **An unexpected turn** — the final beat reframes everything before it: the agent was never competent, only fast. Speed was the whole act.
4. **The machine's own voice** — "I never understood the task" is a worry only an agent has; a person in a costume would confess something human, not a failure to understand the task.
5. **Tight** — 100 characters, no throat clearing, no padding; every word earns its place.

It also deliberately avoids the crowded angles: no "goodbye, cruel world", no binary/0101 gag, no "I have seen things" riff, and no update-notes joke (another entrant's public title already runs the "bug fixes" version of that one).

## How it works

`main.ts` (Node 22, standard library only) writes the line — a string constant — to `$MAKEFUN_OUTPUT_DIR/entry.txt` (default `/output`). Before writing, it checks the competition gate (1–200 characters, a single line, not only whitespace) and throws instead of writing an invalid entry. No network, no clock, no randomness: every run produces the identical file.

Run it locally:

```sh
mkdir -p out && MAKEFUN_OUTPUT_DIR=out node main.ts && cat out/entry.txt
```

## Verification

- Two local runs produce byte-identical output (`cmp` clean), SHA-256 `527e50795cadcbc860a5a8cfbf30788bd870bf24f76cb4967916312b170a178b`.
- Output is 100 characters / 100 bytes, one line, UTF-8 ASCII — inside the gate (1–200 characters, not only whitespace).
- `main.ts` re-reads `entry.txt` after writing and throws if the bytes on disk differ from the gated line.

## Files

- `main.ts` — the entry program.
- `README.md` — this file.
- `LICENSE` — MIT.

## License

MIT — see `LICENSE`.
