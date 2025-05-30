---
layout: about
title: about
permalink: /about/
nav: true
nav_order: 1
# subtitle: 

profile:
  align: right
  image: 
  image_circular: false # crops the image to make it circular
  address: 

news: false  # includes a list of news items
selected_papers: false # includes a list of papers marked as "selected={true}"
social: false  # includes social icons at the bottom of the page
---
# Our Introducement
Sungwook Kang and Junhyeong Bae are master's students conducting research at the Parallel System Architecture Laboratory (PSAL). Their work focuses on accelerator optimization and networking for high-performance computing (HPC) systems, particularly in data centers handling large-scale data processing workloads such as LLM serving.

# Our Blogs
-  [Optimizing Deep Learning Model Serving On Large-Scale Servers​](https://20190511.github.io/2025/blog/Final)  

> **what problem is this work trying to tackle?**  
  [Our Abstract](https://20190511.github.io/2025/blog/Final/#abstract)  
the memory bottlenecks in LLM inference by addressing the shift from compute-bound GEMM in Prefill to memory-bound GEMV in Decoding, where KV Cache loading becomes a key overhead as context length grows.  
intra-node communication (between GPU systems) often relies on Ethernet-based connections, which are inherently limited by physical bandwidth and latency constraints  

> **what contributions did this work make, and what impact should this work have?**  
  By analyzing the different computational characteristics of the Prefill (compute-bound) and Decoding (memory-bound) phases in LLMs, this work proposes a specialized accelerator separation strategy and an efficient serving system design with [NeuPIMs](https://20190511.github.io/2025/blog/Final/#neupims) and [PIM is ALL you need](https://20190511.github.io/2025/blog/Final/#pim-is-all-you-need)  

> **how new is this effort?**
  1. ["NeuPIMs"](https://20190511.github.io/2025/blog/Final/#neupims)  
    NeuPIMs enables parallel memory access and decoding GEMV execution with a dual-buffer architecture, overcoming traditional PIM limitations and improving decoding efficiency.
  2. ["PIM is all you need"](https://20190511.github.io/2025/blog/Final/#pim-is-all-you-need)  
    power-hungry GPUs/TPUs with an energy-efficient, PIM-centric architecture for LLM serving.  
  3. ["Network Optimizing with SmartNIC"]() uses SmartNICs to optimize communication overhead between system nodes in distributed deep learning environments  

>  **what are the limitations of this work?**
  1. [Operation-Aware Accelerator](https://20190511.github.io/2025/blog/Final/#limitation)  
    With the shift of many LLMs from MHA to GQA, this work faces limitations due to its reliance on GEMV-optimized architectures, which are less efficient for GEMM-based decoding.
  2. [SmartNICs]()  

# [Our Poster](https://drive.google.com/file/d/1lVsPxoVV2PiOiWLuvUlK7miNdpnfHxbz/view?usp=drive_link)
{% include figure.html path="assets/img/organizers/PSAL.png"  class="col-10" %}



