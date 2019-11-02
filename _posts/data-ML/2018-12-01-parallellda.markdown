---
title: Parallel LDA
fulltitle: "Implementing Parallalized LDA for Text Classification using OpenMPI"
subtitle: Implementing Parallalized LDA for Text Classification using OpenMPI
category: Machine Learning, Text Mining
layout: post
date: 2018-12-01
img: parallellda.jpg
thumbnail: parallellda-thumbnail.jpg
alt: image-alt
project-date: December 2018
description: In this project, we explored the speedup of parallalizing the LDA algorithm for text classification, by implementing multiple different versions of parallel LDA using OpenMPI, and testing out the performance with different synchronization policies and different numbers of processes. 
story: This project was the final project for the course 15-418 Parallel Computer Architecture and Programming.
---

### Background

Latent Dirichlet Allocation (LDA) is a widely used algorithm in text classification, which clusters word occurrences into latent classes (i.e. topics) after iterations of parameter learning. As the sampling process is extremely computation-heavy for large data sets, we implemented parallel LDA in this project and experimented with its performance.

### LDA at a Glance

![img]({{site.baseurl}}/img/projects/parallellda/parallellda-intro.jpg)

### Method

Parallel LDA workflow:

- Split corpus by document

- Each process runs local Gibbs sampling

- Master gathers updates and send back to each process

![img]({{site.baseurl}}/img/projects/parallellda/parallellda-workflow.jpg)

### Implementation

We implemented two variations of parallelism LDA using the OpenMPI library - the synchronous version and the asynchronous version. We also added staleness in our implementation.

**Synchronous Parallel LDA**: updates broadcasted to all processes

**Asynchronous Parallel LDA**: each process send local updates to master after a few iters, keep on sampling, and updates upon receiving new table

### Results

![img]({{site.baseurl}}/img/projects/parallellda/parallellda-result.jpg)

### Discussion

#### How does the parallelism scale? 
Close to linear speedup until up to 6 procs, and gets smaller after but still achieves 9x with 16 procs.

#### What's the tradeoff between log-likelihood & speed?

Learned parameters will be more “stale” as the staleness gets larger. This gets us faster speed, but sometimes might decrease the objective function (log-likelihood) as a tradeoff.

#### Speedup comparison of sync vs. async

We expected async version to be faster, but since there’s not much work imbalance in sync version, and for async the master takes on more work updating the tables based on messages from each process, the speedup for both are about the same.

### Conclusion

Our implementation of parallel Latent Dirichlet Allocation achieves an overall good speedup compared to the sequential version. For future work, better asynchronous update rules might be designed for better work balance to further improve performance.

### Useful Links

[Source Code](https://github.com/judykong97/Parallel_LDA) \|
[Project Report]({{site.baseurl}}/files/projects/parallellda/Project%20Report.pdf) \| 
[Project Poster]({{site.baseurl}}/files/projects/parallellda/Project%20Poster.pdf)

### Team Members

[Zhixin(Angelica) Feng](https://www.linkedin.com/in/zhixin-angelica-feng)

