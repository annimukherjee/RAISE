# RAISE: Realness Assessment for Image Synthesis and Evaluation  

This repository contains the dataset and code for our paper _RAISE: Realness Assessment for Image Synthesis and Evaluation_, accepted at [MIPR 2025](https://sites.google.com/view/mipr-2025/ieee-mipr).

## Requirements
All the requirements to run our code are specified in the `requirements.txt` file. Here's how to set it up:
```
# 1) Clone the repo and jump into it
> git clone https://github.com/annimukherjee/RAISE.git
> cd RAISE

# 2) Create a clean Conda environment
> conda create -n raise python=3.10

# 3) Activate the environment
> conda activate raise

# 4) Install all dependencies listed in requirements.txt
> pip install -r requirements.txt
```

## RAISE Dataset
The RAISE dataset comprises **600** images out of which **480** are AI generated and **120** are real photographic images along with their corresponding subjective realness ratings as MOS scores. The images and corresponding ratings are made available under the `/dataset` directory. 

There are **510** images in the training set and **90** images in the test set. The real images are named as `r1.png`, `r2.png`, ... , `r120.png` and the AI generated images are named as `f1.png`, `f2.png`, ..., `f480.png`.

## Baseline Models

We provide the training as well as evaluation of four baseline models for performing realness prediction on the RAISE dataset as follows:

### Decision Tree

[Notebook](https://github.com/annimukherjee/RAISE/blob/main/models/00_ml-models/02_ml-features-modelling.ipynb)


### CNN Model

[Train Notebooks](https://github.com/annimukherjee/RAISE/blob/main/models/01_CNN/0_base_cnn-train.ipynb) | [Test Notebook](https://github.com/annimukherjee/RAISE/blob/main/models/01_CNN/1_base_cnn-test.ipynb)


### Neural Network with Pretrained ResNet-18 Features

[Train Notebook](https://github.com/annimukherjee/RAISE/blob/main/models/02_RestNet-18-Exp/0_transf-learning-train.ipynb) | [Test Notebook](https://github.com/annimukherjee/RAISE/blob/main/models/02_RestNet-18-Exp/1_transf-learning-test.ipynb)


### Neural Network with Pretrained ResNet-50 features from JOINT Rationality Branch

[Train Notebook](https://github.com/annimukherjee/RAISE/blob/main/models/04_NN-fine-tuned-JOINT/0_joint-resnet-train.ipynb) | [Test Notebook
](https://github.com/annimukherjee/RAISE/blob/main/models/04_NN-fine-tuned-JOINT/1_joint-resnet-test.ipynb)

## Contact
For questions, please email the corresponding authors:
- Aniruddha Mukherjee: mukh.aniruddha@gmail.com
- Spriha Dubey: sprihadubey2004@gmail.com 

## Citations
If you make use of the RAISE dataset and the code shared in this repository, please cite our paper as:
```
@misc{raise,
      title={RAISE: Realness Assessment for Image Synthesis and Evaluation}, 
      author={Aniruddha Mukherjee and Spriha Dubey and Somdyuti Paul},
      year={2025},
      eprint={2505.19233},
      archivePrefix={arXiv},
      primaryClass={cs.CV},
      url={https://arxiv.org/abs/2505.19233}, 
}
```

Permission is granted for non-commercial use only under `CC-BY-NC`.
