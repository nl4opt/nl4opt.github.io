---
layout: default
title: Getting Started
permalink: /gettingstarted/

---

# Dataset

[Data repository](https://github.com/nl4opt/data)

The novel dataset in this competition has never been publically released. It consists of a total of 600 annotated linear programming (LP) word problems from 6 different domains. For both sub-tasks, it is important to evaluate whether models generalize to unseen problem domains. Therefore, LP problems from the three similar domains of sales, advertising, and investment have been included in both training, validation, and testing splits. On the other hand, problems from three other domains (production, transportation, and health sciences) have been allocated for the test split. By doing so, the test set will test for the generalizability of solutions to new problem domains. Please note that it is against the rules to manually expand the dataset (i.e. change the words of the training data to fit production/transportation/health sciences problems) since the focus of this competition is to leverage a smaller dataset and create a robust solution. However, intelligent methods of augmentation is permitted.

Each dataset instance has an input paragraph describing an LP problem. An example of the input data and its annotations for the two sub-tasks is illustrated below.

### Sub-task 1:

For the first sub-task, the output is the set of entities that correspond to the componenets of the problem. The entities are tagged according to predefined entity types. We will provide the labels in Spacy format and in BIO tagging format.

### Sub-task 2:

For the second sub-task, the inputs are the problem description, its set of problem entities, and the order mapping of variable mentions. The problem entities can be used as context information to guide the semantic parsing task. The ground-truth label annotations consist of the objective declaration and the constraints declarations as shown below. The output of the semantic parser is the meaning representation of those declarations. As shown below, the meaning representation should be converted to a canonical form for evaluation. Participants may either design their own meaning representation or use the representation and conversion scripts from our pilot study.<br><br>

# Starter kit

[Starter kit repository](https://github.com/nl4opt/starter-kit)

The provided "starter kit" includes baseline models, training/evaluation code, data loaders, and scripts to convert data formats (into a canonical format that is used for the evaluation):

**Sub-task 1:** For the named entity recognition sub-task, the baseline model is a fine-tuned Roberta transformer, which achieved an F1-score of 82.57% on the union of in-domain and out-of-domain test sets.

**Sub-task 2:** For the generation sub-task, the baseline model is a BART encoder-decoder that leverages a prompt-guided generation and a copy mechanism to generate a meaning representation of the optimization formulation. For each objective/constraint declaration, a prompt has been created based on the set of problem entities, and the baseline model was trained to complete the prompt and generate the meaning representation. It achieved an accuracy of 38.50% on the combined test set. The meaning representation preserves the semantic and contextual information of the objective and constraint declarations.