# GGCS-MONet

This repository contains the testing code of **GGCS-MONet**, a CNN based solution for SAR Amplitude Despeckling.

if you find it useful and use it for you research, please cite as the following 
```
@ARTICLE{10250969,
  author={Vitale, Sergio and Ferraioli, Giampaolo and Frery, Alejandro C. and Pascazio, Vito and Yue, Dong-Xiao and Xu, Feng},
  journal={IEEE Transactions on Geoscience and Remote Sensing}, 
  title={{SAR} Despeckling Using Multiobjective Neural Network Trained With Generic Statistical Samples}, 
  year={2023},
  volume={61},
  number={},
  pages={1-12},
  doi={10.1109/TGRS.2023.3314857}}
```

GGCS-MONet inglobe the benefit of a multi-objective architecture of [MONet](https://ieeexplore.ieee.org/document/9261137) and a specific training strategy based on the [GGCS simulator](https://ieeexplore.ieee.org/stamp/stamp.jsp?arnumber=8944059)

The 17 layers CNN architecture. 
<p align="center">
 <img src="![immagine](https://github.com/impress-parthenope/GGCS-MONet/assets/85936968/9de093ab-e24a-442c-8c77-22e0379da9b5)" width="700">
</p>
  
The cost function is composed of three terms taking care of spatial and statistical properties of the interferometric phase: a cosine based metric for evaluating similarity between output and reference, a gradient based metric for edges preservation and the Kullback-Leibler divergence between estimated noise distribution and the theoretical one.

<p align="center">
<img src="https://user-images.githubusercontent.com/36993034/197556133-3ce13133-b3ec-4913-a8a9-0ead333e6c7e.png" width=400> 
</p>

<p align="center">
 <img src="https://user-images.githubusercontent.com/36993034/197556216-307418ae-1cd4-4734-b837-61ed111f93d3.png" width = 500>
</p>

An example on simulated data is shown below
Noisy Image| Noise-Free Reference | InSAR-MONet 
:-----------------------------------------|:---------------------------------------:|:--------------------------------------:
<img src="https://user-images.githubusercontent.com/36993034/197556940-3af2a154-d82d-4df3-b18d-bd37b0258bd7.png" width="150"> |<img src="https://user-images.githubusercontent.com/36993034/197557009-a407aea1-8f7c-41a5-834c-87066edace1e.png" width="150"> |<img src="https://user-images.githubusercontent.com/36993034/197557074-e7566a82-f0bf-4853-9776-8ef22aa77c82.png" width="150">

# Team members
 Sergio Vitale    (contact person, sergio.vitale@uniparthenope.it);
 Giampaolo Ferraioli (giampaolo.ferraioli@uniparthenope.it);
 Gilda  Schirinzi (gilda.schirinzi@uniparthenope.it)
 Vito Pascazio (vito.pascazio@uniparthenope.it)
 
# License
Copyright (c) 2022 Dipartimento di Ingegneria and Dipartimento di Scienze e Tecnologie of Università degli Studi di Napoli "Parthenope".

All rights reserved. This work should only be used for nonprofit purposes.

By downloading and/or using any of these files, you implicitly agree to all the
terms of the license, as specified in the document LICENSE.txt
(included in this directory)

# Usage 
* **data** folder contains three samples images with simulated interferometric SAR phases (corresponding to the examples of the paper);
Three differente cases can be tested:
     * small baseline and high coherence (B1, Gamma 4)
     * medium baseline and medium coherence (B2, Gamma 3)
     * large baseline and low coherence (B4, Gamma 1)

* *model* contains trained weigths
* *model.py* contains the model implementation
* *testing.py* is the main script for testing

# Prerequisites
This code is written on Ubuntu system for Python3.7 and uses Pytorch library.

For a correct usage of the code, please install the python environement saved in **./env/monet_pytorch.yml** with the following step:

**Installing Anaconda** (if not already installed)

1. download anaconda3 from https://www.anaconda.com/products/individual#linux
2. from command line, move to the download directory and install the package by:
> sh <Anaconda_downloaded_version>.sh 
and follow the instruction for installation
3. add conda to path
> PATH=~/anaconda3/bin:$PATH

**Installing the conda environment**

The file ./insarmonet_env.yml contains the environemnt for the testing the code. You can easily installing it by command line:

1. move to the folder containing the github repository and open the terminal
2. run the following command
 > conda env create -f insarmonet_env.yml


Once environment has been set up, activate it by command line as well:

1. activate the environemnt from the command line

> conda activate insarmonet_env

2. launch spyder

> spyder

3. goes to the folder containing **testing.py**, edit and run



