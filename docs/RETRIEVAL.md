# docs/RETRIEVAL.md — Hybrid retrieval strategies

## Overview
The system uses three parallel retrievers + fusion for precision and recall.

## 1) BM25 (keyword-based)
When: named entities.
Strength: fast, precise for exact matches.
Weakness: misses semantic similarity.

## 2) Dense retrieval (embedding-based)
When: semantic queries.
Strength: captures paraphrases.
Weakness: slower; requires embeddings.

## 3) Graph traversal (relation-based)
When: multi-hop reasoning.
Strength: captures chains and cross-domain edges.
Weakness: requires well-structured link graph.

## 4) Fusion
Use Reciprocal Rank Fusion (RRF) to combine retriever outputs and deduplicate.

## Task integration (contract)
In each Task prompt, include a retrieval stage that:
1) pulls recent briefs from `briefs/`
2) pulls canonical docs from `docs/` + source-of-truth configs
3) fuses retrieval results before generation

## Caching strategy
- Static corpus (docs/, watchlist.yml, triggers.yml): cache retrieval-friendly representations.
- Daily briefs: incremental updates only.
