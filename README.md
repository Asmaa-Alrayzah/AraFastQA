# AraFastQA


## Arabic Transformer model for Question-Answering based on Few-Shot Learning Approach (AraFastQA)
This repository models and datasets discussed in our paper “….”
Our pretraining code is based on TensorFlow (checked on 1.15), while fine-tuning is based on PyTorch (1.7.1) and Transformers (2.9.0). Note each has its requirements.

## Abstract
…..

## Pre-Trained Models on HugginFace
- AraFastQA-base: [Link](https://huggingface.co/Asmaa-Alrayzah/AraFastQA-base)
- AraFastQA-mini: [Link](https://huggingface.co/Asmaa-Alrayzah/AraFastQA-mini)


## Fine-tuning based on FSL
The FSL tuning has different requirements than pretraining, using HuggingFace's Transformers library. Create a virtual environment and execute

`!pip install -r requirements.txt`

Or, you can install it directly using the following command:

`!pip install torch==1.7.1 transformers==2.9.0  tokenizers==0.7.0 tensorboardX`

Just so you know, if you want to reproduce results from the paper or run with a QASS head in general, questions need to be augmented with a [QUESTION] token <br>  To do so, please run the following command:

`!python qass_preprocess.py --path "../datasets /*"`

This will add a [MASK] token to each question in the training data, which will later be replaced by a [QUESTION] token automatically by the QASS layer implementation.

Note: <br> 
You can download the Arabic QA benchmark datasets (TyDi QA and ARCD) with the QASS layer directly (without  needing to run qass_preprocess.py) from the following command:

`!gdown --id 15t9ClxZNQsFkdFxv9uxKLCiVVx67PhLU --folder`


## Datasets in MRQA structure without QASS layer
Download the Arabic QA benchmark datasets (TyDi QA and ARCD) from the following command:

`!gdown --id 1-uXPl2bpY2ak-b5vSNJFK8XbonjEaRdQ --folder`

## Python version
Using the 8.3 version of Python to run the model is preferable. You can downgrade the Python version using the following commands:

`!apt-get install python3.8 python3.8-distutils`<br>
`!sudo update-alternatives --install /usr/bin/python3 python3 /usr/bin/python3.8 1` <br>
`!sudo apt install python3-pip` <br>
<br>
`!python --version`

# AraFastQA-base Performance

This table presents the final F1 and EM scores for the AraFastQA-base model across different "shots" of training data for the ARCD and TyDi QA datasets.<br>
NOTE: The following results are introduced by conducting fine-tuning based on FSL of this experiment on High Performance Computing (HPC) known as Aziz Supercomputer. 

| Shots    | Measure | ARCD  | TyDi QA |
|----------|---------|-------|---------|
| 16 shot  | F1      | 22.99 | 27.22   |
|          | EM      | 6.8   | 13.73   |
| 32 shot  | F1      | 29.15 | 32.37   |
|          | EM      | 6.22  | 16.9    |
| 64 shot  | F1      | 35.44 | 37.05   |
|          | EM      | 7.7   | 20.54   |
| 128 shot | F1      | 39.14 | 49.03   |
|          | EM      | 8.66  | 27.14   |
| 256 shot | F1      | 41.59 | 65.06   |
|          | EM      | 10.33 | 43.86   |
| 512 shot | F1      | 46.05 | 69.51   |
|          | EM      | 11.66 | 49.83   |
| 1024 shot| F1      | 54.29 | 74.51   |
|          | EM      | 16.47 | 55.91   |
| Full shot| F1      | 73.45 | 84.04   |
|          | EM      | 59.33 | 68.4    |


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

## Bugs or questions?
If you have questions about the code or the paper, please email Asmaa ( asalrayzah@nu.edu.sa). Please feel free to open an issue if you encounter any problems when using the code or want to report a bug. Please try to specify the problem with details so we can help you better and quicker!

