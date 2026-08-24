<img src="docs/pyserini-logo-small.png" width="200" />

# Evaluation Data for Anserini and Pyserini

This repository holds various data and various tools used by [Anserini](http://anserini.io/) and [Pyserini](http://pyserini.io/).

Build the included evaluation tools as follows (you might get warnings, but you can ignore):

```bash
cd eval && tar xvfz trec_eval.9.0.4.tar.gz && cd trec_eval.9.0.4 && make && cd ../..
cd eval && cd ndeval && make && cd ../..
```

## Topics

Topics for various evaluations are stored in [`topics/`](topics/).
Metadata is stored in [`topics.json`](topics.json) and aliases in [`topics-aliases.json`](topics-aliases.json).
In the aliases file, the keys represent canonical topics.

## Qrels

Qrels for various evaluations are stored in [`qrels/`](qrels/).
Metadata is stored in [`qrels.json`](qrels.json) and aliases in [`qrels-aliases.json`](qrels-aliases.json).
In the aliases file, the keys represent canonical topics.

## Historical Notes

❗ At commit [`43add83`](https://github.com/castorini/eval/commit/43add835e20bd66b48f9a640be9bad95a4762d82) (2026/08/09), `topics-and-qrels/` was refactored into separate `topics/` and `qrels/` directories.
At the same time, this repo was renamed from `anserini-tools` to `eval`.
The associated PR is [`eval#118`](https://github.com/castorini/eval/pull/118).
This breaks consumers that depend on fetching a stable `topics-and-qrels/` path (on `master`).
Note that the most obvious solution to add symlinks won't work, as `raw.githubusercontent.com` URLs do not automatically redirect.
Unfortunately, there's no good solution... according to Codex, we either have to fix all downstream consumers or have separate copies of the data.

Anserini commit [`9bfc04b`](https://github.com/castorini/anserini/commit/9bfc04b2d5f22e3acf56edf43d06c1efa5fe2783) (2026/08/11) was the first commit that pinned a specific commit (hence ensuring stability).
The associated PR is [`anserini#3369`](https://github.com/castorini/anserini/pull/3369).
This means that any state of the repo before that commit is likely broken.
