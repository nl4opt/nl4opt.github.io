---
layout: default
title: Blog
permalink: /blog/

---

# 2022-07-05: Introducing the NL4Opt Competition

We are pleased to announce the "Natural Language for Optimization (NL4Opt)" competition will be part of NeurIPS 2022 competition.

**What is the NL4Opt competition?**

Say a local grocery store has limited space and needs to sell certain produces before they spoil. There are also different profit margins for these products and they would like to know how many of each produce to put in the store front to minimize waste. How would they solve such a problem? This is one simple example, but businesses and organizations have traditionally turned to operations research experts to model and make these decisions using standard optimization solvers. Many real-world problems can be modeled and solved by mathematical optimization. In fact, operations research has seen many successful applications such as increasing bike-share ridership and efficiency in urban cities [1, 2], managing wastewater collection and treatment systems [3], or finding a revenue-maximizing pricing strategy for businesses [4].

However, modeling real-world problems into proper formulations as input to optimization solvers is still an iterative and strenuous process. As part of [NeurIPS2022](https://neurips.cc/Conferences/2022/CompetitionTrack), the [https://nl4opt.github.io/](https://nl4opt.github.io/) will explore how NLP methods can automatically translate an optimization problem description into a format that optimization solvers understand. This pipeline will make solvers more accessible and allow non-experts to use them in their decision-making.

**The NL4Opt subtasks**

The competition consists of two tasks: an NER and a generation task.

*The NER task:*

- Recognize and label semantic entities corresponding to the components of the optimization problem

- Takes in a word problem describing the components (decision variables, objective, constraints) and tags the entities

- Preliminary (preprocessing) step to simplify sub-task 2

*The generation task:*

- Takes in labelled entities and order mapping to formulate precise meaning representation

- Convert into format that solvers can understand

- Evaluated on the canonical form

**The NL4Opt dataset**

A novel NLP dataset has been curated by operations research experts. This dataset consists of over a thousand linear programming word problems (LPWP) similar to the waste eduction problem described above and has been labelled for the challenge’s two tasks. Teams of individuals or a group of participants may submit their solutions to either or both tasks. The dataset challenges the participants to build models that can generalize not only to new LPWP problems but also to new problem domains. Baseline approaches and [tutorials](https://nl4opt.github.io/tutorial/) are provided in the starter kits.

**Incentives**

A total of $22,000 USD will be awarded across the two tasks. A workshop will also be hosted at the end of the competition and will be inviting experts and winners as podium speakers. Additionally, we plan to host poster sessions for participants to share their solution. Winning solutions will be shared with the scientific community through a peer-reviewed manuscript summarizing the findings of the competition.

**Logistics of the competition**

The competition is tentatively from July 1st to October 15th with the submission portal opening on July 15th. We look forward to your participation – we encourage you to [register]([Participate | NL4Opt](https://nl4opt.github.io/participate/)) and our organizers will be in touch with you shortly.

For more information regarding the competition details, schedule, eligibility, rules, FAQs, and to get started, visit our competition website linked below! Follow our [social media](https://twitter.com/NL4Opt) and [GitHub discussion forum]( [Discussions · nl4opt/nl4opt-competition · GitHub](https://github.com/nl4opt/nl4opt-competition/discussions)) to keep updated. If you have any questions, please take a look at the FAQ section of our website. For any remaining questions, free to start the discussion on the [GitHub forum]([Discussions · nl4opt/nl4opt-competition · GitHub](https://github.com/nl4opt/nl4opt-competition/discussions)).

Website: [https://nl4opt.github.io/](https://nl4opt.github.io/)

**Special thanks**

The NL4Opt challenge would not be possible without the teams from the University of British Columbia, Ivey Business School and Huawei Technologies Canada.

**References**

1. Beairsto, J., Tian, Y., Zheng, L., Zhao, Q., Hong, J.: Identifying locations for new bike-sharing stations in glasgow: an analysis of spatial equity and demand factors. Annals of GIS 0(0), 1–16 (2021), [Full article: Identifying locations for new bike-sharing stations in Glasgow: an analysis of spatial equity and demand factors](https://doi.org/10.1080/19475683.2021.1936172)

2. Ma, Y., Qin, X., Xu, J., Zou, X.: Research on pricing method of public bicycle service: A case study in guangzhou. In: IEEE International Conference on Service Operations and Logistics, and Informatics (SOLI). pp. 156–161 (2016)

3. Tao, D.Q., Pleau, M., et al.: Analytics and Optimization Reduce Sewage Overflows to Protect Community Waterways in Kentucky. Interfaces 50(1), 7–20 (January 2020), https://ideas.repec.org/a/inm/orinte/v50y2020i1p7-20.html

4. Bitran, G.R., Caldentey, R.A.: An overview of pricing models for revenue management. IEEE Engineering Management Review 44, 134–134 (2016) 
