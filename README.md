#  Interpretable Face Aging: Enhancing Conditional Adversarial Autoencoders with LIME Explanations

This repository was created with the aim of incorporating an Explanatory System in the Conditional Adversarial Autoencoder (CAAE). The main source of inspiration was the paper [Age Progression/Regressionby Conditional Adversarial Autoencoder](https://openaccess.thecvf.com/content_cvpr_2017/html/Zhang_Age_ProgressionRegression_by_CVPR_2017_paper.html) proposed by (Zhang, Song, et al.). Moreover, the paper [xAI-GAN: Enhancing Generative Adversarial Networks via Explainable AI Systems](https://arxiv.org/abs/2002.10438) proposed by (Nagisetyy, Graves, et al.) formed the base of adding xAI methods in CAAE. Finally, thanks to Mattan Serry and the [AgeProgression](https://github.com/mattans/AgeProgression) work, we developed our code in PyTorch.

# Our Paper

This repo contains the codes of the proposed Interpretable Conditional Adversarial Autoencoder (ICAAE) described in the [**Interpretable Face Aging: Enhancing Conditional Adversarial Autoencoders with LIME Explanations**]() paper. The paper is published in the proceedings of the ***2024 IEEE International Conference on Acoustics, Speech, and Signal Processing*** (ICASSP 2024).


# Dataset

The dataset we used for training was the CACD + UTKFace which consists of 21267 images in 7 age classes. FGNET with 1002 images was used for the test purpose. The data folder can be downloaded through [Google Drive](https://drive.google.com/drive/folders/1AvYtsiAiZaO611AMGBK8fSFCqrUlBOOf?usp=sharing).

# Prerequisites

1. Python 3.7
2. Pytorch 1.2.0
3. Captum 0.4.0
4. Lime 0.2.0.1

# Implementation

The control and change of the Explainable Artificial Intelligence system is achieved through the *net.teachSplit()* in mainCAAEsplit_ver2_lime.py script. If it is a need to train the Original CAAE, without the addition of the xAI system, *explainable* is set to **False**. The xAI system is activated by setting *explainable* to **True**. LIME can be added by setting the *explanation_type* to '**lime**'.

# Virtual Environment

```shell
conda create -n icaae python=3.7 anaconda
```

```shell
conda activate icaae
```

```shell
pip install -r requirements.txt
```

# Training

```shell
python mainCAAEsplit_ver2_lime.py --mode train --epochs 140 --input data/CACD_UTKFace --output checkpoints
```
# Testing 

```shell
python mainCAAEsplit_ver2_lime.py --mode test --load checkpoints/epoch140 --input data/FGNET --output results/checkpoints/epoch140 --age <0 to 6> --gender <0 or 1>
```

# Directory Tree
```
LIME-CAAE   
│   consts.py  
│   mainCAAEsplit_ver2_lime.py  
│   modelSplit_v2_lime.py   
│   README.md
│   my_lime_image.py
|   requirements.txt
│   utils.py
|   utils_xai.py
└───data
    └───CACD_UTKFace
    └───FGNET
```

# Author

Feel free to send me a message for any issue.

***Christos Korgialas (ckorgial@csd.auth.gr)***
