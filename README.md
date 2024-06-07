# Probabilistic Programming and Bayesian Computing with PyMC

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/fonnesbeck/bayes_course_june_2024/main) 

Bayesian statistical methods offer a powerful set of tools to tackle a wide variety of data science problems. In addition, the Bayesian approach generates results that are easy to interpret and automatically account for uncertainty in quantities that we wish to estimate or predict. Historically, computational challenges have been a barrier, particularly to new users, but there now exists a mature set of probabilistic programming tools that are both capable and easy to learn. We will use the newest release of PyMC (version 5), but the concepts and approaches that will be taught are portable to any probabilistic programming framework.

This course is intended for practicing and aspiring data scientists and analysts looking to learn how to apply Bayesian statistics and probabilistic programming to their work. It will provide learners with a high-level understanding of Bayesian statistical methods and their potential for use in a variety of applications. They will also gain hands-on experience with applying these methods using PyMC, specifically including the specification, fitting and checking of models applied to a couple of real-world datasets.

This is an introductory course, therefore no direct experience with PyMC or Bayesian statistics will be expected. However, to benefit maximally from the tutorial, learners should have some familiarity with basic statistical modeling (things like regression and estimation) and with core components of the scientific Python stack (e.g. NumPy, pandas and Jupyter). For those with no Python experience, some pre-conference tutorials will be posted to get new users up-and-running. This tutorial will be presented with Jupyter notebooks, allowing participants to run examples and exercises on their own computers. A GitHub repository will be set up 2 weeks prior to SDSS, with instructions on how to set up the Python environment to run the tutorial locally.

As the goal of the tutorial is to get new users up and running with Bayesian methods, the content will be light on theory and focus on the implementation of models, though some statistical background will be provided for context and clarity. Since PyMC is a high-level statistical package, it is easy to gloss over important details of the underlying algorithms. Therefore, the tutorial will begin by solving a simple model using only NumPy and SciPy functions before diving into PyMC. As a capstone to the tutorial, learners will be introduced to "The Bayesian Workflow" to reiterate the important steps in the process, along with useful tips and tricks.

## Computer Setup

This tutorial assumes that you have some form of [Anaconda](https://www.anaconda.com/products/individual#download-section) Python (with Python version 3.11) setup and installed on your system. If you do not, please download and install this on your system before proceeding with the setup. We recommend using the [Miniforge](https://github.com/conda-forge/miniforge#download) distribution of Anaconda, which is a lightweight version of Anaconda that is easier to work with.

The next step is to clone or download the tutorial materials in this repository. If you are familiar with Git, run the clone command:

    git clone https://github.com/fonnesbeck/bayes_course_june_2024.git

otherwise you can [download a zip file](https://github.com/fonnesbeck/bayes_course_june_2024/archive/main.zip) of its contents, and unzip it on your computer.
***
The repository for this tutorial contains a file called `environment.yml` that includes a list of all the packages used for the tutorial. If you run:

    mamba env create

from the main tutorial directory (if you installed Anaconda instead of Miniforge, use `conda` instead of `mamba`), it will create the environment for you and install all of the packages listed. Some Windows users may have difficulty installing two of the packages (`jax` and `numpyro`). If you have trouble with this, you can use the following environment instead:

    mamba env create -f environment_nojax.yml

This environment can be enabled using:

    mamba activate bayes_course  

or 
    
    conda activate bayes_course

Then, you can start **JupyterLab** to access the materials:

    jupyter lab

The binder link above should also provide a working environment.

For those who like to work in VS Code, you can also run Jupyter notebooks from within VS Code. To do this, you will need to install the [Jupyter extension](https://marketplace.visualstudio.com/items?itemName=ms-toolsai.jupyter). Once this is installed, you can open the notebooks in the `notebooks` subdirectory and run them interactively.

## Pre-course Work

In advance of the course, we would like attendees to complete a short homework notebook that will ensure everyone has the requisite baseline knowledge. You can find this Jupyter notebook in the `/notebooks` subdirectory (under `Section0-Pre_Work.ipynb`). There is no need to hand this in to anyone, but please reach out if you have difficulty with any of the problems (or with setting up your computing environment) by creating an [issue](https://github.com/fonnesbeck/bayes_course_june_2024/issues) in this repository, or by emailing.

## Daily Schedule (All times are UK time)

- **8:00 to 9:30** First session
- **9:30 to 9:45** Break ☕
- **9:45 to 11:15** Second session
- **11:15 to 11:30** Break ☕
- **11:30 to 13:00** Third session

## Course Outline

The course comprises ten modules of videoconference lectures, along with short associated hands-on projects to reinforce materials covered during lectures. The sections cover core materials related to Bayesian computation using PyMC, and include:

### Tuesday, June 11

**A Primer on Bayesian Inference**
- Conditional probability and Bayes' formula
- The anatomy of a Bayesian model
- Probability density functions, inverse CDF sampling
- Bayesian comuptation and approximations

**Introduction to Bayesian Models and PyMC** 
- The PyMC API
- My first PyMC model
- PyTensor
  
### Wednesday, June 12

**Markov chain Monte Carlo** 
- Rejection sampling
- MCMC basics
- Metropolis-Hastings samplers
- Gibbs samplers
- Problems with first-generation MCMC methods
- Using gradient information to improve MCMC
- Hamiltonian Monte Carlo
- The NUTS algorithm

**PyMC Model Building**
- Model building in PyMC
- Partial pooling
- Building hierarchical models
- Parameterizations

### Thursday, June 13

**Hierarchical Models**
- Partial pooling
- Random effects
- Prediction

**Model Checking**
- Convergence diagnostics
- Goodness-of-fit checks
- Model comparison

### Friday, June 14

**The Bayesian Workflow** 
- Prior predictive checks
- Iterating models
- Posterior predictive checks
- Generative modeling
- Using the model

**Non-parametric Bayes** 
- Spline models
- Gaussian processes