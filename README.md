# AraFastQA


## Arabic Transformer model for Quesion-Answering based on Few-Shot Learning Approach (AraFastQA)
This repository models and datasets discussed in our paper “….”
Our pretraining code is based on TensorFlow (checked on 1.15), while fine-tuning is based on PyTorch (1.7.1) and Transformers (2.9.0). Note each has its own requirements.

## Abstract
…..

## Pre-Trained Models on HugginFace
- AraFastQA-base: [Link](https://huggingface.co/Asmaa-Alrayzah/AraFastQA-base)
- AraFastQA-mini: [Link](https://huggingface.co/Asmaa-Alrayzah/AraFastQA-mini)


## Tuning based on FSL
The FSL tuning has different requirements than pretraining, as it uses HuggingFace's Transformers library. Create a virtual environment and execute

`!pip install -r requirements.txt`

Please Note: If you want to reproduce results from the paper or run with a QASS head in general, questions need to be augmented with a [QUESTION] token. In order to do so, please run

`!python qass_preprocess.py --path "../datasets /*"`

This will add a [MASK] token to each question in the training data, which will later be replaced by a [QUESTION] token automatically by the QASS layer implementation.

## Datasets in MRQA structure
Download the Arabic QA benchmark datasets (TyDi QA and ARCD) from the following command

`!gdown --id 1-7jj89-HEFu5DIMV9J8mBSKyBvmC-P6U –folder`

## Citation
If you use this work in your research, please cite it using the following BibTeX entry:

```bibtex
@article{YourLastName2023,
  title={...},
  author={...},
  journal={...},
  volume={...},
  number={...},
  pages={...},
  year={2023},
  publisher={...}
}
```

## Contact

For any further inquiries, you can reach me at asalrayzah@gmail.com

