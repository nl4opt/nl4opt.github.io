---
# Feel free to add content and custom Front Matter to this file.

# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Welcome to the NL4Opt competition website

---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>

<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<div class="page-title">
    <div class="title">NL4Opt</div>
        <a href="https://nips.cc/Conferences/2022/">
        <img class="nips-logo" src="figures/NeurIPS_logo.svg" href="https://nips.cc/Conferences/2022/">
        </a>
</div>

You can find the competition rules and answers to commonly asked questions here.

# News

* More details about the NeurIPS 2022 competition (e.g. data, starter kit, tutorial, notebooks, etc...) will be provided soon. Stay tuned!

# Important Dates

The following dates use the [anywhere on earth (AoE)](https://www.timeanddate.com/time/zones/aoe) time zone:

| Event                                                                                                                                    | Date                |
| ---------------------------------------------------------------------------------------------------------------------------------------- | ------------------- |
| **Competition kickoff.** The registration is opened and participants can download the starterkit and the training/validation datasets.   | July 1st, 2022      |
| **Submission available.** The leaderboard and forum are opened, and the submissions are accepted.                                        | July 15th, 2022     |
| **Deadline for submission.**                                                                                                             | October 15th, 2022  |
| **Winners notification.** Winning teams are notified and instructed to provide information that will be included in the workshop report. | October 31st, 2022  |
| **Report submission deadline.**                                                                                                          | November 20th, 2022 |
| **NeurIPS competition workshop.**                                                                                                        | December 2022       |

# Introduction

The Natural Language for Optimization (NL4Opt) NeurIPS 2022 competition aims to improve the accessibility and usability of optimization solvers. The task of converting text description of a problem into proper formulations for optimization solvers can often be time-consuming and require an optimizations research expert. The participants will investigate methods of automating this process to be more efficient and accessible to non-experts. This competition aims to answer the following question: *can learning-based natural language interfaces be leveraged to convert linear programming (LP) word problems into a format that solvers can understand?*

This competition presents **two challenges for ML:** (1) detect problem entities from the problem description and (2) generate a precise meaning representation of the optimization formulation.

# Challenges

The competition is split into two main tasks that are related, but tackled independently. Participants can compete in any subset of these two challenges and the 5 best winning submissions of each task will be awarded (see the Prizes Section below).

The two inter-related tasks are to find an intelligent solution to:

1. detect problem entities from the problem statement,

2. generate a precise meaning representation of the optimization formulation.

## Sub-task 1 - named entity recognition

**The goal of this task** is to recognize the label the semantic entities that correspond to the components of the optimization problem. The solutions of the task will take as input an optimization description as a word problem that describes the decision variables, the objective, and a set of constraints. The multi-sentence word problem input exhibits a high level of ambiguity due to the variability of the linguistic patterns, problem domains, and problem structures. **This first task aims to reduce the ambiguity by detecting and tagging the entities of the optimization problems** such as the objective name, decision variable names, or the constraint limits. This is a preliminary step to simplify the second sub-task and can be seen as a preprocessing task.

**Metric:** F1 score

**Relevant resources:**

- [Review Article - Chinese Named Entity Recognition](https://doi.org/10.1016/j.neucom.2021.10.101 "Persistent link using digital object identifier"). Liu et al., *Neurocomputing*, 2022,

- [A Survey on Deep Learning for Named Entity Recognition](https://doi.ieeecomputersociety.org/10.1109/TKDE.2020.2981314). Li et al., *IEEE Transactions on Knowledge and Data Engineering*, 2022,

- [MeasEval – Extracting Counts and Measurements and their Related Contexts](http://dx.doi.org/10.18653/v1/2021.semeval-1.38). Harper et al., *Association for Computational Linguistics*, 2021,

- [Symlink- Linking Mathematical Symbols to their Descriptions](https://arxiv.org/abs/2202.09695). Lai et al., *arXiv*, 2022.

## Sub-task 2 - generating the precise meaning representation

**The goal of this task** is to take as input the problem description, the labeled semantic entities, and the order mapping of variable mentions and formulate the precise meaning representation. This meaning representation will be converted into a format that solvers can understand. The solutions will be evaluated on the canonical form and conversion scripts from our pilot study has been released as part of the starter kit. We welcome you to create your own meaning representation or use the representation and conversion scripts provided in the starter kit.

**Metric:** Declaration-level mapping accuracy

**Relevant resources:**

- [NLC2CMD Competition: Translating Natural Language to Bash Commands](https://arxiv.org/abs/2103.02523). Agarwal et al., *arXiv*, 2021,

- [CodeBERT: A Pre-Trained Model for Programming and Natural Languages](https://aclanthology.org/2020.findings-emnlp.139). Feng et al., *Findings of the Association for Computational Linguistics: EMNLP 2020*, 2020,

- [Thesis - Learning meaning representations for text generation with deep generative models](https://www.repository.cam.ac.uk/handle/1810/305297). Kris Cao, *University of Cambridge Dissertation*, 2019.

**For more information** regarding the type of data in each sub-task and the resources provided to help you get started, visit the [Getting Started](https://nl4opt.github.io/starterkit/) page of our website.

# Metrics

**Sub-task 1 (named entity recognition):** The solutions will be evaluated on their achieved micro-averaged F1 score:

$$\text{F1} ={2\times P \times R \over P+R},$$

where $$P$$ and $$R$$ are the average precision and average recall averaged over all entity types, respectively.

**Sub-task 2 (generation):** The solutions will be evaluated using an application-specific metric since the task is motivated by the need to precisely formulate the optimization problem. The models will be benchmarked based on the declaration-level mapping accuracy given by:

$$\text{Acc} = 1-\sum_{i=1}^N\frac{\sum_{i=1}^NFP_{i}}{\sum_{i=1}^{N}D_{i}},$$

where $$N$$ is the number of LP problems in the test set. For each LP problem $$i$$, $$D_{i}$$ is the number of ground-truth declarations. The false positive $$FP_{i}$$ is the number of non-matched predicted declarations whereas the false negative $$FN_{i}$$ denotes the number of ground-truth declarations without a match.

# Prizes

A total monetary prize of $22,000 USD will be awarded. The 5 best winning submissions of each task will be awarded the following prizes:

- **1st place:** $6,000

- **2nd place:** $3,000

- **3rd place:** $1,000

- **4th and 5th place:** $500

All participants will receive a certificate of participation. Winners will be invited to give talks at the workshop.
