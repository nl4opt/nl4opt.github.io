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

<div class="figure">
    <img class="tutorial-figure" src="../figures/subtask1.png">
    Overview of how our baseline model generates predictions for subtask 1.
</div>

This pretrained baseline transformer model is adapted from a [popular NER competition](https://multiconer.github.io/) that leverages XLM-RoBERTa-base model which is a multilingual version of RoBERTA.

The model was evaluated on the reserved three new domains (production, science, and transportation) which are not represented in the released train or dev dataset (see rows 1-3 below). It was then also evaluated on 50 reserved samples from the same domain as those released to the participants ("Original Domains" below). Finally, the model was evaluated on the entire test set made up of all reserved sampled described above ("Entire Test Set" below). The leaderboard and final standings will only consider the micro-averaged F1 score (right-most column) of the submitted models on the entire test set. This model achieved the following F1 scores:

|                          | CONST<br/>DIR | LIMIT | OBJ<br/>DIR | OBJ<br/>NAME | PARAM | VAR | MICRO<br/>AVG |
| ------------------------ | ------------- | ----- | ----------- | ------------ | ----- | --- | ------------- |
| **Production<br>**       |               |       |             |              |       |     |               |
| **Science<br>**          |               |       |             |              |       |     |               |
| **Transportation<br>**   |               |       |             |              |       |     |               |
| **Original Domains<br>** |               |       |             |              |       |     |               |
| **Entire Test Set<br>**  |               |       |             |              |       |     | \*            |

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

<div class="figure">
    <img class="tutorial-figure" src="../figures/subtask2.png">
    Overview of how our baseline model generates predictions for subtask 2.
</div>

In the starter kit, you will find the files required to train a baseline model using BART.

## Environment Setup

We have provided a Conda environment file `environment.yml`. To install:

```
conda env create -f environment.yml
conda activate myenv
```

Verify that it was installed:

```
conda env list
```

## Training

The subfolder `./configs` should contain the configuration file for setting up the model configuration and the training hyperparameters. The configuration file `baseline.json` corresponds to the baseline model for subtask 2. To run the training with our configuration:

```
python train.py --config configs/baseline.json
```

The important parameters here are `use_copy`, `per_declaration`,  and `use_prompt`. 

- `use_copy` uses a copy mechanism that computes $P_\text{copy}$ over the input tokens. 
- `per_declaration` controls each training data sample to correspond to a single declaration of a given LP problem instead of the entire formulation (i.e. all declarations in the problem).
- `use_prompt` uses a declaration prompt to focus the generation. For example, the `<OBJ_DIR>` is used as a prompt for generating the objective declaration.

Note that beam search is available as an alternative to greedy search in decoding; however, we found that greedy search worked better.

## Testing

To evaluate the model:

```
python test.py --gpu <gpu id> --checkpoint <checkpoint.mdl> --test-file <test.jsonl>
```

More details about scoring can be found in the `notebooks` folder [here](/notebooks/demo.ipynb). For reference, our baseline model achieves a per-declaration accuracy of `Acc = 0.60` on the test set. Note however that the test set is held out and will not be shared to participants.

For more details, see the README for [subtask-2](https://github.com/nl4opt/nl4opt-subtask2-baseline) for a tutorial on training a baseline BART model.
