# Face Aging by Explainable Conditional Adversarial Autoencoder using LIME

This repository was created with the aim of incorporating an Explanatory System in the Conditional Adversarial Autoencoder (CAAE). The main source of inspiration was the paper [Age Progression/Regressionby Conditional Adversarial Autoencoder](https://openaccess.thecvf.com/content_cvpr_2017/html/Zhang_Age_ProgressionRegression_by_CVPR_2017_paper.html) proposed by (Zhang, Song, et al.). Moreover, the paper [xAI-GAN: Enhancing Generative Adversarial Networks via Explainable AI Systems](https://arxiv.org/abs/2002.10438) proposed by (Nagisetyy, Graves, et al.) formed the base of adding xAI methods in CAAE. Endly, thanks to Mattan Serry and the [AgeProgression](https://github.com/mattans/AgeProgression) work, we devoloped our code in PyTorch.

# Master Thesis

This code was used to implement the experiments of my Master Thesis in Digital Media - Computational Intelligence.

[Master Thesis]()

# Dataset

The dataset we used for training was the CACD + UTKFace which consists of 21267 images in 7 age classes. FGNET with 1002 images used for the test purpose. The data folder can be downloaded through [Google Drive](https://drive.google.com/drive/folders/1AvYtsiAiZaO611AMGBK8fSFCqrUlBOOf?usp=sharing).

# Prerequisites

1. Python 3.7
2. Pytorch 1.2.0
3. Captum 0.4.0
4. Lime 0.2.0.1

# Implementation

The control and change of the Explainable Artificial Intelligence system is achieved through the *net.teachSplit()* in mainCAAEsplit_ver2_lime.py script. If it is a need to train the Original CAAE, without the addition of the xAI system, *explainable* is set to **False**. The xAI system is activated by setting *explainable* to **True**. LIME can be added by setting the *explanation_type* to '**lime**'.

# Virtual Environment

```shell
conda create --name <env> --file requirements.txt
```

# Training

```shell
python mainCAAEsplit_ver2_lime.py --mode train --epochs 200 --input data/CACD_UTKFace --output checkpoints
```
# Testing 

```shell
python mainCAAEsplit_ver2_lime.py --mode test --load checkpoints/epoch200 --input data/FGNET --output results/checkpoints/epoch200 --age <0 or 1> --gender <0 or 1>
```

# Authors

***Christos Korgialas and Constantine Kotropoulos***
