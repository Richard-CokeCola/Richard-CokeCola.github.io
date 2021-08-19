---
title: "Install Pytorch for GPU and CPU using Conda on Ubuntu"
date: 2021-06-17T10:21:38+08:00
tags:  [  " Tutorial " , "AI" ]
---

1. **Install Anaconda or Miniconda depends on your taste.**

   Go to anaconda or miniconda's website and download the .sh file for your system. Go into the terminal use "chmod +x filename" command to the .sh file then run it. Always click yes to finish installation.

2. **Install jupyter**

   conda install -y jupyter

3. **Create the enviroment named torch**

   ```bash
   conda create --name torch python=3.8
   # created a conda enviroment named 'torch'
   ```

   After finished, reopen the terminal

4. **Activate enviroment**

   ```bash
   conda activate torch
   conda install nb_conda
   # Add conda env to jupyter notebook
   python -m ipykernel install --user --name myenv --display-name "Python (myenv)"
   ```

5. **Install Pytorch**

   You can go check [Pytorch's website](https://pytorch.org/get-started/locally/) to see all the installation options.

   * CPU and GPU:

     ```bash
     conda install pytorch torchvision torchaudio cudatoolkit=11.1 -c pytorch -c nvidia
     ```

   * CPU only:

     ```bash
     conda create --name torch python=3.7
     conda install pytorch torchvision torchaudio cpuonly -c pytorch
     ```
     
     

6. **Install other libraries**

   ```
   conda install -c conda-forge opencv
   dependencies:
       - jupyter
       - scikit-learn
       - scipy
       - pandas
       - pandas-datareader
       - matplotlib
       - pillow
       - tqdm
       - requests
       - h5py
       - pyyaml
       - flask
       - boto3
       - pip:
           - bayesian-optimization
           - gym
           - kaggle
   ```
   
   Or, if there is any requirements.txt, just use
   
   ```bash
   pip install -r requirements.txt
   ```
   
   



**Reference:**

https://github.com/jeffheaton/t81_558_deep_learning/blob/master/install/pytorch-install-jul-2020.ipynb

https://pytorch.org/get-started/locally/

