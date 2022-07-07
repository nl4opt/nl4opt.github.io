---
# Feel free to add content and custom Front Matter to this file.

# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Welcome to the NL4Opt competition website

---

<script src="https://polyfill.io/v3/polyfill.min.js?features=es6"></script>

<script id="MathJax-script" async src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-mml-chtml.js"></script>

<div class="page-title">
    <div class="title"> <img class="nips-logo" src="figures/nl4optlogo.jpg" height="200"></div>
        <a href="https://nips.cc/Conferences/2022/">
        <img class="nips-logo" src="figures/NeurIPS_logo.svg" width="150" height="75">
        </a>
</div>

You can find the competition [rules](https://nl4opt.github.io/rules/) and answers to [commonly asked questions](https://nl4opt.github.io/faq/) on this website.

# News

### 2022-07-05 Announcements

1. The data and starter-kits have been released!
* [Data repository](https://github.com/nl4opt/nl4opt-competition)
* [Sub-task 1 repository](https://github.com/nl4opt/nl4opt-subtask1-baseline)
* [Sub-task 2 repository](https://github.com/nl4opt/nl4opt-subtask2-baseline)
2. The organizers are planning to host a Q&A session the week after the submission portal opens (July 18th to 22nd). If you are running into issues with your submission or have any other questions, please feel free to join us. More details will be shared closer to the date! 

3. Keep an eye out on your email for the instructions for submission in the upcoming week! The submission portal opens on July 15th. 

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

- [MultiCoNER Competition](https://multiconer.github.io/). *SemEval 2022 Task 11.*

- [Hugging Face Tutorial.](https://huggingface.co/course/chapter0/1?fw=pt) *Hugging Face.*

- [PyTorch Tutorial - Named Entity Recognition Tagging](https://cs230.stanford.edu/blog/namedentity/). *Stanford Blog.*

- [Keras Tutorial - Named Entity Recognition using Transformers](https://keras.io/examples/nlp/ner_transformers/). *Keras.*

- [Tutorial - How to Fine-Tune BERT for Named Entity Recognition (NER)](https://skimai.com/how-to-fine-tune-bert-for-named-entity-recognition-ner/). *Skimai.*

## Sub-task 2 - generating the precise meaning representation

**The goal of this task** is to take as input the problem description, the labeled semantic entities, and the order mapping of variable mentions and formulate the precise meaning representation. This meaning representation will be converted into a format that solvers can understand. The solutions will be evaluated on the canonical form and conversion scripts from our pilot study has been released as part of the starter kit. We welcome you to create your own meaning representation or use the representation and conversion scripts provided in the starter kit.

**Metric:** Declaration-level mapping accuracy

**Relevant resources:**

- [Natural Language Processing with Transformers: Building Language Applications with Hugging Face.](https://www.amazon.ca/Natural-Language-Processing-Transformers-Applications/dp/1098103246) Tunstall et al., *(O’Reilly Media, 2022)*

- [Hugging Face Tutorial.](https://huggingface.co/course/chapter0/1?fw=pt) *Hugging Face.*

- [Using different decoding methods for language generation with Transformers.](https://colab.research.google.com/github/huggingface/blog/blob/main/notebooks/02_how_to_generate.ipynb) Alexander et al., *(Colab notebook).*

- [Constrained Language Models Yield Few-Shot Semantic Parsers.](https://aclanthology.org/2021.emnlp-main.608.pdf) Shin et al., *ACL Anthology.*

- [The Power of Prompt Tuning for Low-Resource Semantic Parsing.](https://arxiv.org/abs/2110.08525) Schucher et al., *arXiv.*

- [Text-to-Table: A New Way of Information Extraction.](https://aclanthology.org/2022.acl-long.180.pdf) Wu et al., *ACL Anthology.*

- [CodeBERT: A Pre-Trained Model for Programming and Natural Languages.](https://aclanthology.org/2020.findings-emnlp.139/) Feng et al., *Findings of the Association for Computational Linguistics: EMNLP 2020.*

- [Few-Shot Semantic Parsing with Language Models Trained On Code.](https://arxiv.org/abs/2112.08696) Shin et al., *arXiv.*

- [PICARD: Parsing Incrementally for Constrained Auto-Regressive Decoding from Language Models.](https://aclanthology.org/2021.emnlp-main.779/) Scholak et al., *ACL Anthology.*

**For more information** regarding the type of data in each sub-task and the resources provided to help you get started, visit the [Getting Started](https://nl4opt.github.io/getttingstarted/) page of our website.

# Metrics

**Sub-task 1 (named entity recognition):** The solutions will be evaluated on their achieved micro-averaged F1 score:

$$\text{F1} ={2\times P \times R \over P+R},$$

where $$P$$ and $$R$$ are the average precision and average recall averaged over all entity types, respectively.

**Sub-task 2 (generation):** The solutions will be evaluated using an application-specific metric since the task is motivated by the need to precisely formulate the optimization problem. The models will be benchmarked based on the declaration-level mapping accuracy given by:

$$\text{Acc} = 1-\frac{\sum_{i=1}^N\text{FP}_{i} + \text{FN}_i}{\sum_{i=1}^{N}D_{i}},$$

where $$N$$ is the number of LP problems in the test set. For each LP problem $$i$$, $$D_{i}$$ is the number of ground-truth declarations. The false positive $$\text{FP}_{i}$$ is the number of non-matched predicted declarations whereas the false negative $$\text{FN}_{i}$$ denotes the number of excess unmatched ground-truth declarations. In other words, false negatives are counted when there are more ground-truth declarations than predicted declarations. A false positive is counted when there is a predicted declaration that does not match any ground-truth declaration.

# Prizes

A total monetary prize of $22,000 USD will be awarded. The 5 best winning submissions of each task will be awarded the following prizes:

- **1st place:** $6,000

- **2nd place:** $3,000

- **3rd place:** $1,000

- **4th and 5th place:** $500

All participants will receive a certificate of participation. Winners will be invited to give talks at the workshop.
