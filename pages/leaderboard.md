```yaml
layout: default
title: Leaderboard
permalink: /leaderboard/
```

# Winners of Nl4Opt

## <u>Subtask 1</u>

### 1st place: Infrrd AI Lab

- **Team members**: JiangLong He, Mamatha N., Shiv Vignesh, Deepak Kumar, Akshay Uppal

- **Affiliation**: Infrrd

- **Method:** Ensemble learning with text augmentation and segment shuffling

- **Test F1-score:** 0.939

### 2nd place: mcmc

- **Team members**: Kangxu Wang, Ze Chen, Jiewen Zheng

- **Affiliation**: OPD

- **Method:** Ensemble learning with fast gradient method and sentence retokenization

- **Test F1-score:** 0.933

### 3rd place: PingAn-zhiniao

- **Team members**: Qi Zeng

- **Affiliation**: PingAn International Smart City

- **Method:** Global pointer and multi-head decoder

- **Test F1-score:** 0.932

### 4th place: Long

- **Team members**: Jiayu Liu, Longhu Qin, Yuting Ning, Tong Xiao, Shangzi Xue, Zhenya Huang, Qi Liu, Enhong Chen, Jinze Wu

- **Affiliation**: BDAA-BASE

- **Method:** Ensemble learning with adversarial training and post processing

- **Test F1-score:** 0.931

### 5th place: VTCC-NLP

- **Team members**: Dung Dong-Xuan

- **Affiliation**: Viettel Cyberspace Center, Viettel Group

- **Method:** Ensemble learning

- **Test F1-score:** 0.929

## <u>Subtask 2</u>

### 1st place: UIUC-NLP

- **Team members**: Neeraj Gangwar, Nickvash Kani

- **Affiliation**: University of Illinois Urbana-Champaign

- **Method:** Tagged input and decode all-at-once strategy

- **Test Accuracy:** 0.899

### 2nd place: Sjang

- **Team members**: Sanghwan Jang

- **Affiliation**: POSTECH

- **Method:** Learn entity tag embedding and data augmentation

- **Test Accuracy:** 0.878

### 3rd place: Long

- **Team members**: Jiayu Liu, Longhu Qin, Yuting Ning, Tong Xiao, Shangzi Xue, Zhenya Huang, Qi Liu, Enhong Chen, Jinze Wu

- **Affiliation**: BDAA-BASE

- **Method:** Prompt re-design + data augmentation + adversarial training

- **Test Accuracy:** 0.867

### 4th place: PingAn-zhiniao

- **Team members**: Xiuyuan Yang, Yixiu Wang

- **Affiliation**: PingAn International Smart City

- **Method:** Data augmentation and dropout regularization

- **Test Accuracy:** 0.866

### 5th place: Infrrd AI Lab

- **Team members**: JiangLong He, Mamatha N., Shiv Vignesh, Deepak Kumar, Akshay Uppal

- **Affiliation**: Infrrd

- **Method:** Multitask training with input preprocessing

- **Test Accuracy:** 0.780

# Leaderboard

The score is based on the performance of the models ran by the organizers on the same training and evaluation server.

## Sub-task 1

| Rank | Team Name                   | Affiliation(s)                   | F1 Score  | Team Members |
| ---- | --------------------------- | -------------------------------- | --------- | ------------ |
| 1    | **Infrrd AI Lab**           | **Infrrd**                       | **0.939** |              |
| 2    | **mcmc**                    | **OPD**                          | **0.933** |              |
| 3    | **PingAn-zhiniao**          | **PingAn Technology**            | **0.932** |              |
| 4    | **Long**                    | **BDAA-BASE**                    | **0.931** |              |
| 5    | **VTCC-NLP**                | **Viettel**                      | **0.929** |              |
| 6    | Sjang                       | POSTECH                          | 0.927     |              |
| 7    | DeepBlueAI                  | DeepBlueAI                       | 0.921     |              |
| 8    | TeamFid                     | Fidelity                         | 0.920     |              |
| 9    | KKKKKi                      | Netease                          | 0.917     |              |
| 10   | holajoa                     | Imperial College London          | 0.910     |              |
| 11   | Dream                       |                                  | 0.884     |              |
| -    | LeNam                       | VNUHCM                           | -         |              |
| -    | Try1try                     | GWU                              | -         |              |
| -    | BK                          |                                  | -         |              |
| -    | UIUC-NLP                    | UIUC                             | -         |              |
| -    | Baseline (XLM-RoBERTa-base) | Nl4Opt                           | -         |              |
| -    | CTRI_ysy                    | China Telecom Research Institute | -         |              |
| -    | CUFE                        | Cairo University                 | -         |              |
| -    | macd                        |                                  | -         |              |
| -    | rs                          |                                  | -         |              |

**Bold** names indicate winning teams, only re-run submissions are ranked.

*\* Details and a tutorial of the baseline can be found in the [Tutorial page](https://nl4opt.github.io/tutorial/).*

- For this challenge, the **micro-averaged F1 score** is the evaluation metric. This measure is described in detail in the metrics section of our [homepage](https://nl4opt.github.io/).

## Sub-task 2

| Rank | Team Name          | Affiliation(s)        | Accuracy  | Team Members |
| ---- | ------------------ | --------------------- | --------- | ------------ |
| 1    | **UIUC-NLP**       | **UIUC**              | **0.899** |              |
| 2    | **Sjang**          | **POSTECH**           | **0.878** |              |
| 3    | **Long**           | **BDAA-BASE**         | **0.867** |              |
| 4    | **PingAn-zhiniao** | **PingAn Technology** | **0.866** |              |
| 5    | **Infrrd AI Lab**  | **Infrrd**            | **0.780** |              |
| 6    | KKKKKi             | Netease               | 0.815     |              |
| -    | Baseline (BART)    | NL4Opt                | -         |              |
| -    | Dream              |                       | -         |              |
| -    | CUFE               |                       | -         |              |
| -    | November           | FSU-Jena              | -         |              |

**Bold** names indicate winning teams, only re-run submissions are ranked.

*\* Details and a tutorial of the baseline can be found in the [Tutorial page](https://nl4opt.github.io/tutorial/).*

- For this challenge, the **declaration-level mapping accuracy** is the evaluation metric. This measure is described in detail in the metrics section of our [homepage](https://nl4opt.github.io/).
