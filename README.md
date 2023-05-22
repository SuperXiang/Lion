# Lion: Adversarial Distillation of Closed-Source Large Language Model

<p align="center" width="100%">
<a ><img src="pics/Lion.jpg" alt="Lion" style="width: 20%; min-width: 200px; display: block; margin: auto;"></a>
</p>

<p align="center">Lion (generated by stable diffusion 2.1)</p>

[![Code License](https://img.shields.io/badge/code%20license-MIT-green)](https://github.com/YJiangcm/Lion/blob/master/LICENSE)
[![Data License](https://img.shields.io/badge/Data%20License-CC%20By%20NC%204.0-red.svg)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/DATA_LICENSE)
[![Weight Diff License](https://img.shields.io/badge/Weight%20Diff%20License-CC%20By%20NC%204.0-yellow)](https://github.com/tatsu-lab/stanford_alpaca/blob/main/WEIGHT_DIFF_LICENSE)
[![Python 3.9+](https://img.shields.io/badge/python-3.9+-blue.svg)](https://www.python.org/downloads/release/python-390/)

**Usage and License Notices**: Like [Alpaca](https://github.com/tatsu-lab/stanford_alpaca), Lion is intended and licensed for research use only. 
<!-- The dataset is CC BY NC 4.0 (allowing only non-commercial use) and models trained using the dataset should not be used outside of research purposes.  -->
<!-- The weight diff is also CC BY NC 4.0 (allowing only non-commercial use). -->

**arXiv preprint**: https://arxiv.org/abs/2211.13873


## News
- :pray: Due to the reason that our team members are perparing for the PhD Qualifying Exam, we apologize for any possible delay in responding to your questions.
We will try our best to resopnse to any of your questions and concerns.
- :blush:

## Overview
<p align="center">
  <img width="700" height="320" src="https://github.com/YJiangcm/Lion/blob/master/pics/overview.jpg">
</p>

The high-level overview of our framework, where we craft a compact Student LLM based on a superior closed-source LLM that serves three roles: the **Teacher**, the **Referee**, and the **Generator**. From left to right, there are three stages in an iteration:  
1) an _imitation_ stage to align the student’s response with the teacher’s response;  
2) a _discrimination_ stage to identify hard samples;  
3) A _generation_ stage to produce new hard samples for escalating the challenges presented to the student model.

## Recovering Lion weights


## Fine-tuning



## Inference


## Evaluation

### Automatic Evaluation with GPT-4
we leverage GPT-4 to automatically rate the response quality (with scores from 1 to 10) between two models on 80 unseen [Vicuna-Instructions](https://github.com/lm-sys/FastChat/blob/main/fastchat/eval/table/question.jsonl).
ChatGPT has been chosen as the reference model to estimate the relative capability of diverse LLMs against it. The relative score is reported in percentage, computed as the ratio of the sum of scores.

**Relative Overall Response Quality**:

<p align="center">
  <img width="500" height="250" src="https://github.com/YJiangcm/Lion/blob/master/pics/relative_quality_overall.jpg">
</p>

**Relative Response Quality of Diverse Task Categories**:

<p align="center">
  <img width="700" height="330" src="https://github.com/YJiangcm/Lion/blob/master/pics/relative_quality_category.jpg">
</p>

### Human Evaluation with Alignment Criteria
We employ the alignment criteria proposed by Askell et al. (2021), which define that an assistant is considered aligned if it is characterized by being helpful, honest, and
harmless (HHH). We performed a human evaluation on 252 [UserOriented-Instructions](https://github.com/yizhongw/self-instruct/blob/main/human_eval/user_oriented_instructions.jsonl). To estimate the won rate, we compare the frequency of won, tie, and lost between each pair
of models below.

<p align="center">
  <img width="500" height="300" src="https://github.com/YJiangcm/Lion/blob/master/pics/252task_win.jpg">
</p>


## Citation
Please cite the repo if you use the code in this repo.

```
@misc{alpaca,
  author = {Rohan Taori and Ishaan Gulrajani and Tianyi Zhang and Yann Dubois and Xuechen Li and Carlos Guestrin and Percy Liang and Tatsunori B. Hashimoto },
  title = {Stanford Alpaca: An Instruction-following LLaMA model},
  year = {2023},
  publisher = {GitHub},
  journal = {GitHub repository},
  howpublished = {\url{https://github.com/tatsu-lab/stanford_alpaca}},
}
```
