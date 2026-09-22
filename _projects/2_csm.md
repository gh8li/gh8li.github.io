---
layout: page
title: GCSM-BU
description: Duplicate-free continuous subgraph matching for batch updates on GPUs.
importance: 2
category: research
related_publications: false
---

**Efficient GPU-Based Continuous Subgraph Matching on Batch Updates**  
Guanghua Li and Xibo Sun (equal contribution), Qiong Luo, and Lijun Chang  
**APWeb 2026**

[Paper PDF]({{ '/assets/pdf/gcsm-bu.pdf' | relative_url }}) · [Presentation]({{ '/assets/pdf/gcsm-bu-slides.pdf' | relative_url }}) · [Code](https://github.com/gh8li/GCSM-BU)

### Motivation

Dynamic graphs change through edge insertions and deletions. Continuous subgraph matching identifies the matches that appear or disappear after these updates. Processing each updated edge independently can repeat work and produce duplicate matches when updates arrive in batches.

### Query-oriented matching

Our **QO-CSM** formulation groups updates into delta relations associated with query edges and processes these relations in order. This avoids duplicate matches by construction, without the extra bookkeeping structures and explicit duplicate-removal step required by update-oriented batch processing.

**GCSM-BU** implements this approach on the GPU for **batch updates**. Its design combines:

- **Two-level indexing** for each query-edge delta relation to narrow the matching search.
- **Dynamic semi-BFS**, which begins with parallel breadth-first search and switches to depth-first search once intermediate results reach a threshold, balancing parallelism against GPU memory use.
- **Backtracking flattening** for tail leaf vertices to reduce load imbalance between GPU warps.

### Evaluation

The camera-ready paper reports speedups of **up to two orders of magnitude over state-of-the-art CPU-based CSM methods** on the evaluated batch-update workloads. It also reports better overall performance than the evaluated GPU update-oriented methods and their query-oriented adaptations.

**Topics:** dynamic graphs · incremental query processing · batch updates · GPU algorithms
