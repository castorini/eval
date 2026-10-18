# RETECO v1.1 Track 1 topics and qrels

These files contain only the public **train and dev** splits of the official
[RETECO SemEval-2027 dataset](https://huggingface.co/datasets/DataScience-UIBK/RETECO-SemEval2027),
pinned to revision [`c21e10ba8aa60eaa201f60fc4604364469c5ec17`](https://huggingface.co/datasets/DataScience-UIBK/RETECO-SemEval2027/tree/c21e10ba8aa60eaa201f60fc4604364469c5ec17).
They cover 13 domains, with one topic/qrel pair per domain, split, and subtrack:

- `reteco-v1.1-track1a-{domain}.{train|dev}`: temporal queries from
  `track1_tempo/{domain}/examples_{split}.jsonl` and `qrels_{split}.txt`.
- `reteco-v1.1-track1b-{domain}.{train|dev}`: step instructions from
  `track1_tempo/{domain}/steps_{split}.jsonl` and `qrels_steps_{split}.txt`.

Topic IDs are the official example/step IDs. Queries and instructions are
converted to `ID<TAB>text` (embedded tabs and line breaks replaced by spaces),
then gzip-compressed. Qrels are byte-for-byte copies of the pinned official
TREC qrels; document IDs match the
[Track 1 prebuilt indexes](https://huggingface.co/datasets/castorini/prebuilt-indexes-reteco).
There are 52 topic/qrel pairs in all: 5,706 topics and 12,235 judgments.
**No Track 2 or hidden test data is included.**

The source dataset distinguishes corpus and Q&A text (CC BY-SA 4.0, with
attribution to the original Stack Exchange authors) from RETECO annotations,
including qrels (CC BY 4.0). See its
[dataset card](https://huggingface.co/datasets/DataScience-UIBK/RETECO-SemEval2027)
for full attribution and citation information.
