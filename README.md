# [RAISE: Realness Assessment for Image Synthesis and Evaluation](https://arxiv.org/pdf/2505.19233)  

This repository contains the dataset and code for our paper _RAISE: Realness Assessment for Image Synthesis and Evaluation_, accepted at [MIPR 2025](https://sites.google.com/view/mipr-2025/ieee-mipr).

## Requirements

All dependencies are listed in `requirements.txt`. We recommend using Conda for environment management. Here's how to set it up:


```bash
# 1. Clone this repository
git clone https://github.com/annimukherjee/RAISE.git
cd RAISE

# 2. Create and activate a Conda environment
conda create -n raise python=3.10 -y
conda activate raise

# 3. Install required packages
pip install -r requirements.txt
```

## RAISE Dataset
The RAISE dataset comprises **600** images out of which **480** are AI generated and **120** are real photographic images along with their corresponding subjective realness ratings as MOS scores. The images and corresponding ratings are made available under the `/dataset` directory. 

There are **510** images in the training set and **90** images in the test set.

  **Image files**:
* Real images: `r1.png`–`r120.png`
* AI-generated images: `f1.png`–`f480.png`


### Dataset Structure

```
dataset/
├── images/
│   ├── test_images/
│   │   ├── f104.png
│   │   ├── ...
│   │   └── r83.png
│   └── train_images/
│       ├── f1.png
│       ├── ...
│       └── r115.png
└── ratings/
    ├── test.csv
    └── train.csv
```

## Baseline Models

We provide the training as well as evaluation of the following baseline models for performing realness prediction on the RAISE dataset:


| Model                                           | Training Notebook                                                                     | Testing Notebook                                                                  |
| ----------------------------------------------- | ------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------- |
| Decision Tree (handcrafted features)            | [02\_ml-features-modelling.ipynb](models/00_ML-FeatDesign/02_ml-features-modelling.ipynb) |                                                                                   |
| CNN                              | [0\_base\_cnn-train.ipynb](models/01_CNN-FeatLearning/0_base_cnn-train.ipynb)                      | [1\_base\_cnn-test.ipynb](models/01_CNN-FeatLearning/1_base_cnn-test.ipynb)                    |
| Transfer Learning (ResNet-18)                   | [0\_transf-learning-train.ipynb](models/02_RestNet-18-Transf-Learn/0_transf-learning-train.ipynb)   | [1\_transf-learning-test.ipynb](models/02_RestNet-18-Transf-Learn/1_transf-learning-test.ipynb) |
| JOINT Fine-Tuned (JOINT Rationality Branch) | [0\_joint-resnet-train.ipynb](models/04_NN-fine-tuned-JOINT/0_joint-resnet-train.ipynb)      | [1\_joint-resnet-test.ipynb](models/04_NN-fine-tuned-JOINT/1_joint-resnet-test.ipynb)    |


A few important considerations for JOINT Fine-Tuned:

 - Chen et al. ([pdf](https://ieeexplore.ieee.org/document/10771738)) provide the weights to their JOINT Model (`JOINT_2024.pth`) in their [official implementation](https://github.com/zijianchen98/AGIN/tree/main). The weights can be found linked to in their [`README file`](https://github.com/zijianchen98/AGIN/blob/main/README.md). You can also directly download it from [here](https://onedrive.live.com/?redeem=aHR0cHM6Ly8xZHJ2Lm1zL3UvYy8wYzIxOTFjYjAxY2JmMDAyL0VjX2xuY0N4R1paQ25qb2NUNDAtc24wQjVTcmcwekZuNkgtOTVFb3B2eEpJelE%5FZT10YWlUOVI&cid=0C2191CB01CBF002&id=C2191CB01CBF002%21sc09de5cf19b142969e3a1c4f8d3eb27d&parId=C2191CB01CBF002%21s10403dccf95e47979e25d26520e84d7b&o=OneUp) (same link). Please place these weights in a new folder called `./models/04_NN-fine-tuned-JOINT/jointweights/`. 
 - Also, please download the [JOINT.py file](https://github.com/zijianchen98/AGIN/blob/main/JOINT/models/JOINT.py) from Chen et al.'s ([pdf](https://ieeexplore.ieee.org/document/10771738)) [official implementation](https://github.com/zijianchen98/AGIN/tree/main) and place this file in the `./models/04_NN-fine-tuned-JOINT/` directory.




## Contact
For questions, please email the corresponding authors:
* **Aniruddha Mukherjee**: [mukh.aniruddha@gmail.com](mailto:mukh.aniruddha@gmail.com)
* **Spriha Dubey**: [sprihadubey2004@gmail.com](mailto:sprihadubey2004@gmail.com)

## Citations

If you make use of the RAISE dataset or the code shared in this repository, please cite our paper as:

```bibtex
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

## License

This project is provided for **non-commercial use only**.

You may use, copy, modify, and share this project for **personal, educational, or research purposes**.  
**Commercial use of any part of this project is strictly prohibited** without explicit written permission from the authors.

---

*For questions about the dataset, models, or reproduction of results, please open an issue or contact the authors directly.*
