Introduction

This repository contains the PyTorch implementation of two research papers presented at COLING 2022 and EMNLP 2022 on domain adaptation for Question Answering (QA).

The main idea is to make QA models (like BERT) perform better when moved from a general dataset (e.g., SQuAD) to a new domain (e.g., healthcare, legal, finance) — without requiring large labeled datasets.

We explore two approaches:

QC4QA (Question Classification for QA)

Classifies questions into types (e.g., “what”, “when”, “who”) using both source and target data.

Uses self-supervised training with pseudo-labels to reduce the gap between domains.

Improves adaptation by aligning similar question types across domains.

QADA (QA Domain Adaptation with Self-Supervision)

Adds data augmentation in hidden space (e.g., synonym sampling, context dropout).

Uses contrastive learning with attention-based features to separate correct answers from noise.

Achieves strong improvements on multiple QA benchmarks.

Both methods show significant gains over standard fine-tuning and other domain adaptation baselines.

Data & Requirements

Datasets (with question classes) and pretrained models are available here
.

Dependencies: PyTorch, Hugging Face Transformers, pytorch_pretrained_bert.

Workflow

Train a base QA model (e.g., on SQuAD).

(Optional) Run question classification to cluster question types.

Adapt the model using:

QC4QA (classification-based)

QADA (hidden space augmentation + contrastive learning)

Evaluate performance on your target dataset.

Results
<img width="833" height="409" alt="image" src="https://github.com/user-attachments/assets/2d90f892-e6f9-44ae-826a-3ac3a36a51c7" />

Both QC4QA and QADA improve accuracy and generalization across domains, showing the value of self-supervised adaptation for QA.

Credits

This work builds on Hugging Face’s Transformers library and CASe
.
