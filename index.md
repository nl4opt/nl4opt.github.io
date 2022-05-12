---
# Feel free to add content and custom Front Matter to this file.

# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Welcome to the NL4Opt competition website

---
<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>
<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

You can find the competition rules and answers to commonly asked questions here.

More details about the NeurIPS 2022 competition (e.g. data, starter kit, tutorial, notebooks, etc...) will be provided soon. Stay tuned!

# Important Dates

The following dates use the [anywhere on earth (AoE)](https://www.timeanddate.com/time/zones/aoe) time zone:

| Event | Date |
|-----|----|
|**Competition kickoff.** The registration is opened and participants can download the starterkit and the training/validation datasets.|July 1st, 2022|
|**Submission available.** The leaderboard and forum are opened, and the submissions are accepted.|July 15th, 2022|
|**Deadline for submission.**|October 15th, 2022|
|**Winners notification.** Winning teams are notified and instructed to provide information that will be included in the workshop report.| October 31st, 2022|
|**Report submission deadline.**| November 20th, 2022|
|**NeurIPS competition workshop.**|December 2022|

# Introduction 

The Natural Language for Optimization (NL4Opt) NeurIPS 2022 competition aims to improve the accessibility and usability of optimization solvers. The task of converting text description of a problem into proper formulations for optimization solvers can often be time-consuming and require an optimizations research expert. The participants will investigate methods of automating this process to be more efficient and accessible to non-experts. This competition aims to answer the following question: *can learning-based natural language interfaces be leveraged to convert linear programming (LP) word problems into a format that solvers can understand?*

This competition presents two sub-tasks (or tracks): (1) detect problem entities from the problem description and (2) generate a precise meaning representation of the optimization formulation.

# Challenges

The competition is split into two main tasks. Specifically, to leverage learning-based natural language interfaces to:

1. detect problem entities from the problem statement,

2. generate a precise meaning representation of the optimization formulation.

# Metrics

**Sub-task 1 (named entity recognition):** The solutions will be evaluated on their achieved micro-averaged F1-score:

$$F1 ={2\times P \times R \over P+R},$$

where $$P$$ and $$R$$ are the average precision and average recall averaged over all entity types, respectively.

**Sub-task 2 (generation):** The solutions will be evaluated using an application-specific metric since the task is motivated by the need to precisely formulate the optimization problem. The models will be benchmarked based on the declaration-level mapping accuracy given by:

$$\text{Acc} = 1-\sum_{i=1}^N\frac{\sum_{i=1}^NFP_{i}}{\sum_{i=1}^{N}D_{i}},$$

where $$N$$ is the number of LP problems in the test set. For each LP problem $$i$$, $$D_{i}$$ is the number of ground-truth declarations. The false positive $$FP_{i}$$ is the number of non-matched predicted declarations whereas the false negative $$FN_{i}$$ denotes the number of ground-truth declarations without a match.

# Prizes

A total monetary prize of \$22,000 USD will be awarded. The 5 best winning submissions of each task will be awarded the following prizes:

* **1st place:** \$6,000

* **2nd place:** \$3,000

* **3rd place:** \$1,000

* **4th and 5th place:** $500

All participants will receive a certificate of participation. Winners will be invited to give talks at the workshop.
