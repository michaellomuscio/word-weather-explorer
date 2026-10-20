# Word Weather explorer

An interactive explorer of how the language around "AI" shifted from early 2022 through the third quarter of 2026, in news coverage and in research abstracts.

**Open it:** https://michaellomuscio.github.io/word-weather-explorer/

Pick a community, a word, and a quarter. The explorer shows the word's nearest neighbors in that quarter (with how stable each one is across bootstrap replicates), how far the word had moved from its early-2022 meaning (with a 90% interval and a test against a shuffled-time control), the date it crossed the halfway point of its move, and its position between pairs of poles such as hype and skepticism.

## What it is built from

Aggregates only: neighbor lists, distances, dates, positions, and counts. The page contains no text from the sources and makes no network requests. It is one self-contained HTML file and works offline.

- **News:** the GDELT Project (https://www.gdeltproject.org/), Web News NGrams 3.0. 196,498 articles from a panel of English-language news sites.
- **Research:** arXiv metadata (titles and abstracts, CC0) in cs.AI, cs.CL, cs.LG, cs.CY, and cs.HC. 341,935 abstracts.

The models are skip-gram word2vec, written from scratch in NumPy and trained per quarter in a shared frame. They were validated on meaning shifts planted into the same text, and on a known event: the explorer dates Twitter's rename to X to the right quarter.

## About

Word Weather is a study by Michael Lomuscio for [Fullstack Educator](https://fullstackeducator.substack.com/), run with Claude Code.
