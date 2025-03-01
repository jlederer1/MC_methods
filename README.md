# Monte Carlo (MC) Methods
- Demo of various MC methods relevant for Deep Learning (DL) 
- Programmed for the seminar 'Concepts in Deep Learning' at the University of Osnabrück (2024/2025) 
- By the group "Latent Architects", Hyerim Hwang and Jakob Lederer.

## Overview
The repo contains demos on different MC methods in application:

### MC Simulation 
The notebook `MC-simulations.ipynb` demonstrates the power of MC simulations. It includes an examples of how to use MC to estimate combinatorial event probabilities in card games. 

### MC Sampling
The notebook `MC-sampling.ipynb` demonstrates different Monte Carlo sampling methods:
- **Rejection Sampling**
- **Importance Sampling**
- **Markov Chain Monte Carlo (MCMC)** (Metropolis-Hastings)

The samples are vizualized and compared by performance on simple functional probability distributions.

The notebook `MC-sampling_animation.ipynb` vizualized the three sampling procedures.

The notebook `MCMC-sampling_discrete` demonstates an adaption of the Metropolis-Hasting algorithm for sampling constraint combinatorial objects, specifically knowledge spaces. In contrast to the previous notebooks, this one adresses a problem which is not solvable through analytical means and RS and IM are not applicable.

### MC Dropout (MCDP)

The notebook `MC-dropout_deterministic` focuses on MCDP, a technique used to estimate model uncertainty in deep learning. It demonstrates how to implement MC Dropout in a neural network to evaluate its performance. In this case a concolutional net was trained on a determnisitic classification task (cifar-10). The notebook includes code to train/load the model, apply dropout during inference, and analyzing the results. Due to bad training results, the MCDP evaluation yields no meaningful results, though.

The notebook `MC-dropout_probabilistic` applies MCDP to a probabilitic transformer model designed for representation learning in "Knowledge Space Theory". The output of the model is a sequence of tokens. The symmetric difference of target sequence and generated sequences is the performance metric. In this case MCDP was used to improve the decoder's predictions through majority votes over multiple stochastic forward passes.
It significantly enhances prediction accuracy, as the nature of the task itself is probabilistic, i.e. knowledge structures are inherently uncertain, and different knowledge states (model output) may correspond to the same observable responses (model input).

## Setup 
This demo is compatible with **Python 3.XX+**. It is recommended to use a virtual environment to manage dependencies.

1. **Clone the repository**:
   ```bash
   git clone https://github.com/jlederer1/MC_methods
   cd MC_methods
   ```

2. ### Setup Conda for Windows & macOS
   ##### **Miniforge (Apple Silicon optimized) - Recommended**
   ```bash
   # Download and install Miniforge (optimized for Apple Silicon)
   curl -L -O https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh
   bash Miniforge3-MacOSX-arm64.sh
   ```
   ##### **Miniconda (Windows & macOS)**
   ```bash
   # Download and install Miniconda (lightweight Anaconda alternative)
   curl -L -O https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-arm64.sh  # macOS
   curl -L -O https://repo.anaconda.com/miniconda/Miniconda3-latest-Windows-x86_64.exe  # Windows (manual install)
   ```

3. Create a virtual environment and install the requirements:

   ```bash
   conda create -n cidl_mc_env python=3.9
   conda activate cidl_mc_env
   ```

4. Install dependancies via the provided yml and post_install.sh or from the terminal directly:
   ```bash 
   conda env update --file environment.yml
   source post_install.sh
   ```
   or manually on windows:
   ```bash
   conda install -c conda-forge python=3.9 numpy matplotlib scipy ipykernel ipython scikit-learn pip
   conda install -c conda-forge pytorch==2.1 torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
   pip install --no-cache-dir git+https://github.com/jlederer1/DKST.git@main
   ```
5. Download Models and Dataset

   Some of the notebooks require the trained models and synthetic datasets to run. Please download the necessary files from MyShare:

   [Download Models and Datasets](https://myshare.uni-osnabrueck.de/d/a59c01dbfaf14769bb2d/)

   After downloading, place the files into the appropriate directories:

   - Models: `data/models/`
   - Datasets: `data/datasets/`