---
layout: default
title: Submissions
permalink: /submissions/


---

# Submission


## Server Specs
We will use a GPU instance on Lambda Labs to test your submissions, the instance has 1x A6000 (48GB) with 14 vCPUs, and 100 GiB RAM. Please feel free to test your code on the their server to ensure your submissions are successful.


## Instructions

Please upload your submission to your Google Drive folder using the link you received in the registration email. In your Google Drive folder, you need to create folders with name `subtask1` and/or `subtask2` depending on which task you want to submit for. In each subtask folder, you may have up to 3 sub-folders (one for each submission). In each submission folder, you must have a script with name `evaluate.sh` containing all necessary command, including setting up the environments, installing necessary dependencies, and evaluting your models on the test data. We recommend using [conda](https://docs.conda.io/en/latest/miniconda.html) or [docker](https://docs.docker.com/get-started/) to setting up the environments (they will be pre-installed on the instance).

The test data files will be copied into your submission folder with filename `test.txt` for subtask1 and `test.jsonl` for subtask2 with the same format as the training and development set. Please ensure you output the the evaluation results (micro f1/accuracy) into a text file named `results.out` containing a single line with the corresponding score (e.g. 0.60), we will use this to update the [Leaderboard](https://nl4opt.github.io/leaderboard/). After evaluation, you will see a output file with name `evaluation.out` containing the shell output for `evaluate.sh` in each submission folder. See below for an example of the structure of your submission folder after evaluation, please ensure that all submission files is under a sub-folder even if you only have one submission. 

```
Team Name
│
└───subtask1
│   │
│   └───task1_submission1
│   │    │   test.txt
│   │    │   evaluate.sh
│   │    │   results.out
│   │    │   evaluation.out
│   │    │   ...
│   │
│   └───task1_submission2
│   │    │   test.txt
│   │    │   evaluate.sh
│   │    │   results.out
│   │    │   evaluation.out
│   │    │   ...
│   │
│   └───task1_submission3
│   │    │   test.txt
│        │   evaluate.sh
│        │   results.out
│        │   evaluation.out
│        │   ...
│   
└───subtask2
    │
    └───task2_submission1
    │    │   test.jsonl
    │    │   evaluate.sh
    │    │   results.out
    │    │   evaluation.out
    │    │   ...
    │
    └───task2_submission2
    │    │   test.jsonl
    │    │   evaluate.sh
    │    │   results.out
    │    │   evaluation.out
    │    │   ...
    │
    └───task2_submission3
         │   test.jsonl
         │   evaluate.sh
         │   results.out
         │   evaluation.out
         │   ...
```

Please ensure that all file and folder names are correct, you can refer to our [evaluation script](https://github.com/nl4opt/nl4opt-competition/blob/main/evaluate_submission.sh) for details. Lastly, please ensure your script finish execution in a reasonable amount of time (<10 min), and refrain from downloading unnecessarily large files to the local file system.

## Tips
If you don't want to upload your code to Google Drive, you can download your submission files in your script `evaluate.sh` to the local directory (e.g. using wget). We will be erasing all data on the instance after each evaluation session.



