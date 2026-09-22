---
layout: page
title: Vora
description: Subgraph queries beyond GPU memory with vector-based execution.
importance: 1
category: research
related_publications: false
---

**A Vector-Based Engine for Scalable GPU-Accelerated Subgraph Query Processing**  
Guanghua Li, Hao Zhang, and Qiong Luo  
**Accepted at ICDE 2027**

[Paper PDF]({{ '/assets/pdf/vora.pdf' | relative_url }})

### Motivation

Subgraph queries are a core operation in graph databases, but their large search spaces and irregular memory accesses make them expensive. GPU implementations must also manage limited device memory and produce results that can feed the rest of a database query pipeline.

**Vora** is a C++ subgraph query engine that processes large graphs on a single GPU. It supports both count-only execution and materialized matches in a columnar representation.

### Design

- **Vector-based execution.** VectorFlux, a lightweight library built on Thrust and RAPIDS Memory Manager, provides vector containers, non-owning views, and data-parallel operators. Programmer-controlled fusion reduces intermediate materialization and global-memory traffic.
- **Database operators.** Expansion, semi-join, and anti-join operations compose into subgraph queries and return columnar results for downstream processing.
- **Execution beyond device memory.** Graph data resides in host memory or on disk. Physical partitioning and runtime logical shards divide a query into local tasks whose input shards meet an explicit GPU memory constraint.
- **Query decomposition.** An optimizer searches for a decomposition using CPU–GPU transfer volume as its heuristic objective.

### Evaluation

The accepted paper evaluates Vora on the Labelled Subgraph Query Benchmark (LSQB), including scale factors from 1 to 1000, using a machine with two AMD EPYC 7302 CPUs and one NVIDIA RTX 3090 GPU. It reports speedups of **up to 12× over optimized CPU systems** and **up to 7× over the best GPU baseline**, while processing graphs that exceed GPU memory capacity by orders of magnitude. These are peak results across the evaluated workloads, rather than uniform speedups for every query.

**Topics:** graph databases · GPU query processing · vectorized execution · out-of-core processing
