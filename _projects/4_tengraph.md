---
layout: page
title: TenGraph
description: A tensor-based graph query engine with one codebase for CPUs and GPUs.
importance: 3
category: research
related_publications: false
---

**A Tensor-Based Graph Query Engine**  
Guanghua Li, Hao Zhang, Xibo Sun, Qiong Luo, and Yuanyuan Zhu  
**Proceedings of the VLDB Endowment, 17(13): 4571–4584, 2024**

[Paper PDF]({{ '/assets/pdf/tengraph.pdf' | relative_url }}) · [Presentation]({{ '/assets/pdf/tengraph-slides.pdf' | relative_url }}) · [DOI](https://doi.org/10.14778/3704965.3704967)

**Code availability:** Source code is not publicly available due to intellectual property restrictions.

### Motivation

Graph queries combine subgraph matching with operations such as filtering, projection, and aggregation. Their irregular access patterns make efficient execution difficult. At the same time, deep learning frameworks already provide highly optimized tensor operations for modern processors.

**TenGraph** explores whether those tensor runtimes can also serve as a foundation for graph query processing. Built on PyTorch, it runs the same query-processing code on multicore CPUs and GPUs.

### Design

- **Tensor storage.** One-dimensional tensors represent graph topology, property values, and intermediate query results. The compressed unique source (CUS) format supports batched neighbor access and edge-existence checks.
- **Batched graph operations.** Tensor programs implement expansion (join), expand-into (semi-join), and anti-expand-into (anti-join) over batches of vertices.
- **Complete query pipelines.** Filtering, projection, aggregation, and ordering compose with matching operations to support graph queries beyond standalone subgraph enumeration.
- **Hardware portability.** PyTorch's tensor runtime supplies optimized implementations for the underlying processor, reducing the need for separate CPU and GPU query engines.

### Evaluation

The paper evaluates graph query benchmark workloads against CPU- and GPU-based systems, including LDBC SNB Business Intelligence queries. Its reported GPU-versus-CPU speedup for TenGraph is **50–100×**, alongside comparisons with other graph and query-processing systems. This result concerns the paper's evaluated workloads; it is not a guarantee for every query or dataset.

**Topics:** graph databases · tensor computation · PyTorch · CPU/GPU execution
