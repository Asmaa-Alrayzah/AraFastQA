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

`!gdown --id 1k9t8tVFt1Ix1qnUoumKCqNR_kl794ad2 --folder`


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

