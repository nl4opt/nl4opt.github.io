---
layout: default
title: FAQ
permalink: /faq/
---

# FAQ

We have listed some frequently asked questions below. If you still have any further questions, please refer to the [Contact](https://nl4opt.github.io/contact/) page of the website to reach our organizers.

**Q**: *How do I participate in the competition?*

You just need to register by filling out the registration form in the [Participate](https://nl4opt.github.io/participate/) page. On the first page, submit your team name, contact email address, and each participant must read through and accept the [Rules](https://nl4opt.github.io/rules/) of the competition. On the second page, enter your each participant's name, affiliation, and email address as formatted in the description of the form. After the registration is complete, you will receive an ID code that will help us identify your submissions or your team's. You may then download the starter kit and get started!

**Q**: *How many members can we have on a team?*

There is no limit to the number of members on a team.

**Q**: *I do not have a team. Can I still participate?*

Yes, we welcome individuals as well as teams to participate.

**Q**:  *Can we use other datasets?*

- Using proprietary datasets or proprietary language models (ones only you and your affiliations have access to, or those behind a paywall) are NOT permitted.

- However, open-sourced datasets are permitted for pre-training purposes only. For example, you can use open-sourced pre-trained transformers or language models on HuggingFace such as BERT.

- You are not allowed to manually extend the given dataset for supervised training purposes since the focus of the competition is to be able to learn the task under low-resource setting.

- Automatic data augmentation that creates variants of the provided dataset instances is permitted. You must however indicate so in the description of your submission and explain how it helps improve the performance of robustness of your model. For more information. read the "Use of Data" in the "Rules" section of this website.

**Q**: *What do I need to make a submission?*

* Make sure you include the following in your submission:
  
  * Same ID code given after registration to identify their multiple submissions.
  
  * A Poetry configuration to manage the participant's Python library dependencies in a deterministic way. Please refer to the template in the starter kit and tutorial for a step-by-step guide.
  
  * A binary file for the trained model.
  
  * If the output of your model format is different from that of the baseline model provided im the starter kit, please provide a conversion script. Please refer to the tutorial for more details.
  
  * For the second sub-task. if you used a different meaning representation. please provide a script to convert their model prediction to the canonical format used for evaluation. Refer to the example/default conversion script in the starter kit.
  
  * Winning submissions will be required to include a brief description of your method.

* Follow the submission protocol details on the website.

**Q**: *What impact will my work have?*

We created this competition to explore the use of NLP for improving the accessibility and usability of optimization solvers. We want to allow non-experts to describe their optimization problem in natural language and automatically translate the description to an input formulation that solvers can understand.

**Q**: *Has anything like this been done before?*

This dataset is unique and the tasks have never been done before.

**Q**: *How was the data curated?*

The data was created by 20 AI engineers and operation research experts over a 3-month period. Specific guidelines were followed to ensure the diversity of problem types and language patterns. Experts manually revised any incorrect or missing entries and an inter-annotator agreement was verified to ensure the quality of the annotation. Special care was taken to make sure that each problem did not include any inappropriate language or sensitive information like names of real people, products, or companies.

**Q**: *What are the prizes?*

We will provide a total monetary prize of \$22000. The 5 best winning submission of each task will be awarded the following prizes (USD currency):

* **1st place**: \$6000

* **2nd place**: \$3000

* **3rd place**: \$1000

* **4th and 5th places**: \$500
