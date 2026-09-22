---
layout: about
permalink: /
title: about
subtitle: Ph.D. Student · HKUST (Guangzhou) · Data Systems
profile:
  align: right
  image: profile_pic.jpg
  image_circular: true
  more_info: >
    <p>gli945@connect.hkust-gz.edu.cn</p>
selected_papers: true
social: true
announcements:
  enabled: false
  scrollable: false
  limit:
latest_posts:
  enabled: false
  scrollable: false
  limit:
---

I am **Guanghua Li**, a Ph.D. student in Data Science and Analytics at **The Hong Kong University of Science and Technology (Guangzhou)**, advised by **Prof. Qiong Luo**. I expect to graduate in January 2027.
  
I build **GPU-accelerated data systems** for graph queries and multi-vector retrieval. My research focuses on turning irregular, data-intensive query workloads into efficient parallel execution while keeping systems practical to program and scalable to large datasets. My work spans tensor-based graph query processing, subgraph queries beyond GPU memory, and late-interaction retrieval for text and multimodal data.

Looking further ahead, my long-term interest is in **data systems for the AI era**—how data should be managed, retrieved, and processed to provide reliable and efficient infrastructure for AI applications.

Previously, I was a research assistant in the Database Research Group at The Chinese University of Hong Kong, advised by Prof. Jeffrey Xu Yu. I received my bachelor’s degree in Computer Science and Technology from Wuhan University in 2022, where I was advised by Prof. Yuanyuan Zhu.

### Research

- **[Vora]({{ '/projects/1_vora/' | relative_url }})** — a vector-based subgraph query engine that uses a single GPU to process graphs larger than device memory. Accepted at ICDE 2027.
- **[GCSM-BU]({{ '/projects/2_csm/' | relative_url }})** — GPU continuous subgraph matching for batch updates, using a query-oriented formulation to avoid duplicate matches. APWeb 2026.
- **[TenGraph]({{ '/projects/4_tengraph/' | relative_url }})** — a graph query engine built from PyTorch tensor operations, with one codebase for multicore CPUs and GPUs. PVLDB 2024.
- **[VectorHit]({{ '/projects/3_vectorhit/' | relative_url }})** — ongoing research on GPU multi-vector retrieval, using cross-vector support to reduce candidate scoring work.

For research inquiries, email **[gli945@connect.hkust-gz.edu.cn](mailto:gli945@connect.hkust-gz.edu.cn)**. See my [CV]({{ '/cv/' | relative_url }}) for education and research experience.
