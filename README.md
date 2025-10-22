# Rebus Dataset

The **Rebus Dataset** is a collection of 221 rebus puzzle images, each annotated with corresponding textual solutions and metadata.  
It was introduced as part of the paper:

> **Reasoning Riddles: How Explainability Reveals Cognitive Limits in Vision-Language Models**  
> *Prahitha Movva, 2025*  
> [arXiv:2510.02780](https://arxiv.org/abs/2510.02780)

The dataset is designed to support research in **visual reasoning, multimodal interpretability, and cognitive evaluation** of vision–language models.

---

## Dataset Structure

- **Images:** 221 rebus puzzles (`0001.jpg`-`0221.jpg`)
- **Metadata:** Provided in `rebus_dataset.csv` with the following fields:
  - `filename`: image filename (e.g., `0001.jpg`)
  - `solution`: canonical textual solution to the rebus
  - `alternate_solutions`: list of acceptable alternate phrasings
  - `category`: one or more cognitive or linguistic transformation types (e.g., *Spatial Encoding*, *Phonetic Transformation*)
  - `exact_spelling`: whether the image spelling exactly matches the intended phrase
  - `theme`: high-level semantic group (e.g., *idioms and expressions*, *food and cuisine*, *common phrases*)

---

## Example Entry

| filename | solution | alternate_solutions | category | exact_spelling | theme |
|-----------|-----------|--------------------|-----------|----------------|--------|
| 0001.jpg  | You're on mute | ["You are on mute"] | Spatial Encoding, Absence Reasoning | No | common_phrase |
---
## Usage
Load the dataset programmatically using the 🤗 Datasets library:
```python
from datasets import load_dataset

dataset = load_dataset("pmovva/rebus-puzzles")
example = dataset["train"][0]
example["image"].show()
print(example)
```
If you use this dataset in your research or publications, please cite the accompanying paper:
```
@inproceedings{
movva2025reasoning,
title={Reasoning Riddles: How Explainability Reveals Cognitive Limits in Vision-Language Models},
author={Prahitha Movva},
booktitle={The First Workshop on the Application of LLM Explainability to Reasoning and Planning},
year={2025},
url={https://openreview.net/forum?id=c5FgKxcwMP}
}
```
