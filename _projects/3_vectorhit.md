---
layout: page
title: VectorHit
description: GPU multi-vector retrieval with cross-vector support and batched refinement.
importance: 4
category: research
related_publications: false
---

**GPU-Efficient Multi-Vector Retrieval with Cross-Vector Support**  
**Ongoing research**

### Motivation

Late-interaction retrieval models represent a query and a document as sets of vectors. Under MaxSim scoring, each query vector finds its best match in the document, and those similarities are summed. This preserves fine-grained matching information but makes candidate scoring much more expensive than single-vector search.

**VectorHit** studies how to reduce this work while exposing large, independent batches of computation to the GPU.

### Approach

- **Cross-vector support.** Retrieve a wider neighborhood for each query vector, then keep documents supported by multiple distinct query vectors. This filters weakly supported candidates before expensive document scoring.
- **Query-adaptive vector selection.** Use informative query vectors for approximate scoring, particularly when queries contain many vectors.
- **Progressive refinement.** Apply increasingly accurate scoring to progressively smaller candidate sets, ending with high-accuracy MaxSim evaluation.
- **Batched GPU execution.** Separate candidate discovery from document scoring so refinement can run in bulk rather than following a score-dependent graph traversal.

### Preliminary findings

The current draft evaluates MS MARCO v1, LoTTe pooled, OK-VQA, and EVQA. At selected operating points, support-aware candidate generation reduces average candidate-set size by **12.1–44.9%** relative to conventional union-based generation while matching or improving both qrel candidate coverage and exact-MaxSim candidate Recall@100.

A controlled EVQA replay experiment also finds **4.75–5.05× higher scoring throughput** when the same document-score evaluations are executed as independent bulk work instead of online graph traversal. This is a scoring-schedule comparison, not an end-to-end retrieval speedup.

These findings are from ongoing work and may change as the evaluation develops.

**Topics:** vector search · late interaction · MaxSim · multimodal retrieval · GPU systems
