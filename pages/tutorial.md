---
layout: default
title: Tutorial
permalink: /tutorial/

---

# Tutorial

This tutorial page goes through the process to register and submission. It then gives a tutorial on how to set up the baseline of each subtask.

If you have further questions, we encourage you to refer to the [FAQ page](https://nl4opt.github.io/faq/) and use our [forum](https://github.com/nl4opt/nl4opt/discussions) for discussion.

# 1. Registration

To register for this competition, head to the [Participate page](https://nl4opt.github.io/participate/) and follow the instructions. Please read through the competition rules before you accept to abide by them. After completing and submitting the form, your team will receive an email in the "team" email address provided in the first page of the registration form. Confirm the contents of your submission by double-checking the table attached in the email. If the contents are incorrect, you may edit the response of your registration following a link provided in the email. The "Team Name" field is the text used to identify your submission and publish to the leaderboards.

# 2. Submission

After your registration, within two work days (PST), you will receive an email with instructions for the submission protocol and a link to a cloud storage folder accessible only by the organizers and your team. You will upload your scripts and transformers or language models to this folder and they will be evaluated every Monday and Friday (PST) throughout the competition.

# 3a. Subtask-1 (NER) Baseline Tutorial

This pretrained baseline transformer model is adapted from a popular NER competition [(MultiCoNER)](https://multiconer.github.io/) that leverages XLM-RoBERTa-base model which is a multilingual version of RoBERTA.

The model was evaluated on the reserved three new domains (production, science, and transportation) which are not represented in the released train or dev dataset (see rows 1-3 below). It was then also evaluated on 50 reserved samples from the same domain as those released to the participants ("Original Domains" below). Finally, the model was evaluated on the entire test set made up of all reserved sampled described above ("Entire Test Set" below). The leaderboard and final standings will only consider the micro-averaged F1 score (right-most column) of the submitted models on the entire test set. This model achieved the following F1 scores:

|                                | CONST<br/>DIR | LIMIT  | OBJ<br/>DIR | OBJ<br/>NAME | PARAM  | VAR    | MICRO<br/>AVG |
| ------------------------------ | ------------- | ------ | ----------- | ------------ | ------ | ------ | ------------- |
| **Production<br>(n=49)**       | 0.8205        | 0.9262 | 1.000       | 0.2295       | 0.9567 | 0.7122 | 0.8068        |
| **Science<br>(n=50)**          | 0.8759        | 0.8992 | 0.6667      | 0.000        | 0.8249 | 0.7881 | 0.7890        |
| **Transportation<br>(n=50)**   | 0.8083        | 0.8757 | 0.7619      | 0.0899       | 0.9034 | 0.7881 | 0.7849        |
| **Original Domains<br>(n=50)** | 0.8764        | 0.8808 | 0.8571      | 0.8286       | 0.9215 | 0.8270 | 0.8659        |
| **Entire Test Set<br>(n=199)** | 0.8411        | 0.8933 | 0.8679      | 0.4947       | 0.9012 | 0.7792 | 0.8126*       |

*\* Value that will be reported on the leaderboards page and used for the final evaluation when determining the winners.*

## Clone the repo from git

Run the following command to clone the repository containing the scripts to create the baseline model.

The current repository is empty and all relevant baseline scripts will be released by July 1st on AoE timezone.

`git clone https://github.com/nl4opt/nl4opt-competition.git`

## Setting up environment using conda

Create a conda environment for the NER task and install the required packages:

`conda create --name nl4opt-ner python=3.9.12`

`conda activate nl4opt-ner`

`cd nl4opt-competition/ner_task/baseline`

`pip install -r requirements_ner.txt`

## Train and evaluate the model

Execute the following commands to train, fine-tune, and evaluate the model on the development set. Participants will not have access to the test set that is used for model evaluation and leaderboard updates.

## Training the model

`python train_model.py --train ./data/train/train.txt --dev ./data/dev/dev.txt --out_dir ./trained_model --model_name xlmr_lr_0.0001 --gpus 1 --epochs 25 --encoder_model xlm-roberta-base --batch_size 64 --lr 0.0001`

## Fine-tuning the model

`python fine_tune.py --train ./data/train/train.txt --out_dir ./trained_model --model_name xlmr_lr_0.0001 --gpus 1 --epochs 15 --encoder_model xlm-roberta-base --batch_size 64 --lr 0.0001 --model ./trained_model/xlmr_lr_0.0001/lightning_logs/version_0`

## Evaluating the model on the dev set

`python evaluate.py --test ./data/dev/dev.txt --out_dir ./trained_model --model_name xlmr_lr_0.0001 --gpus 1 --encoder_model xlm-roberta-base --batch_size 64 --model ./trained_model/xlmr_lr_0.0001/lightning_logs/version_1`

# 3b. Subtask-2 (Generation) Baseline Tutorial

Coming soon...