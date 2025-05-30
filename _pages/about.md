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
# About Us
Sungwook Kang and Junhyeong Bae are master's students conducting research at the Parallel System Architecture Laboratory (PSAL). Their work focuses on accelerator optimization and networking for high-performance computing (HPC) systems, particularly in data centers handling large-scale data processing workloads such as LLM serving.

# Research Review Highlights 
> **Read the Full Blog Post**   
[Optimizing Deep Learning Model Serving On Large-Scale Servers​](https://20190511.github.io/2025/blog/Final)  

> **What problems are these works trying to tackle?**  
  [Abstract](https://20190511.github.io/2025/blog/Final/#abstract)  
1. The memory bottlenecks in LLM inference by addressing the shift from compute-bound GEMM in Prefill to memory-bound GEMV in Decoding, where KV Cache loading becomes a key overhead as context length grows.  
2. Intra-node communication (between GPU systems) often relies on Ethernet-based connections, which are inherently limited by physical bandwidth and latency constraints  

> **What contributions did these works make, and what impact should these works have?**  
  1. By analyzing the different computational characteristics of the Prefill (compute-bound) and Decoding (memory-bound) phases in LLMs, this work proposes a specialized accelerator separation strategy and an efficient serving system design with [NeuPIMs](https://20190511.github.io/2025/blog/Final/#neupims) and [PIM is ALL you need](https://20190511.github.io/2025/blog/Final/#pim-is-all-you-need)  
  2. By addressing the inefficiencies in traditional Ring-AllReduce communication and the sparsity of modern AI models, these works propose SmartNIC-based solutions: [DirectReduce](https://20190511.github.io/2025/blog/Final/#smartnic-for-ring-allreduce) offloads reduction operations to SmartNICs with architectural enhancements to minimize data transfers and host interruptions, while [OmNICCL](https://20190511.github.io/2025/blog/Final/#zero-sparse-allreduce-and-smartnic-offloading) introduces Zero-Sparse AllReduce and a memory-efficient aggregation framework leveraging Direct Cache Access and double buffering. Together, they reduce communication overhead, optimize SmartNIC resource utilization, and improve scalability and efficiency in distributed deep learning.

> **How new are these efforts?**
  1. [NeuPIMs](https://20190511.github.io/2025/blog/Final/#neupims)  
    NeuPIMs enables parallel memory access and decoding GEMV execution with a dual-buffer architecture, overcoming traditional PIM limitations and improving decoding efficiency.
  2. [PIM is all you need](https://20190511.github.io/2025/blog/Final/#pim-is-all-you-need)  
    power-hungry GPUs/TPUs with an energy-efficient, PIM-centric architecture for LLM serving.  
  3. [DirectReduce](https://20190511.github.io/2025/blog/Final/#smartnic-for-ring-allreduce)   
    Introduces a novel design by offloading the reduction operation of Ring-AllReduce directly onto SmartNICs, eliminating host CPU/GPU involvement and reducing unnecessary data movement.
  4. [OmNICCL](https://20190511.github.io/2025/blog/Final/#zero-sparse-allreduce-and-smartnic-offloading)   
    Proposes the first integration of Zero-Sparse AllReduce, leveraging sparsity to minimize communication, combined with SmartNIC-based aggregation and memory layout optimizations.

>  **What are the limitations of these works?**
  1. [Operation-Aware Accelerator](https://20190511.github.io/2025/blog/Final/#limitation)  
    With the shift of many LLMs from MHA to GQA, this work faces limitations due to its reliance on GEMV-optimized architectures, which are less efficient for GEMM-based decoding.
  2. [SmartNICs](https://20190511.github.io/2025/blog/Final/#limitation-of-smartnic)   
    Current SmartNIC performance and memory limitations cap the effectiveness of both DirectReduce and OmNICCL.

# [Poster Overview](https://drive.google.com/file/d/1lVsPxoVV2PiOiWLuvUlK7miNdpnfHxbz/view?usp=drive_link)
{% include figure.html path="assets/img/organizers/PSAL.png"  class="col-10" %}



