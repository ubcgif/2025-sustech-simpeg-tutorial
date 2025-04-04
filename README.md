**[summary](#summary) | [prerequisites](#prerequisites) | [setup](#setup) | [resources](#resources) | [license](#license)**

# Geophysical inversions with SimPEG: Tutorial at SUSTech in April 2025

[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ubcgif/2025-sustech-simpeg-tutorial/main)
[![License](https://img.shields.io/github/license/ubcgif/2025-sustech-simpeg-tutorial.svg)](https://github.com/ubcgif/2025-sustech-simpeg-tutorial/blob/main/LICENSE)

## Summary

In this tutorial, we will provide a hand-on overview of using SimPEG to simulate and invert geophysical data. The examples we plan to work through use Direct Current (DC) Resistivity and Induced Polarization (IP) data from the Century Zinc Deposit in Australia.

Starting from field data in a text file we will learn how to
- load those data into SimPEG
- construct a survey object that contains the geometry of the sources and receivers
- set up and run a forward simulation
- define the inverse problem consisting of a data misfit and regularization
- run an inversion and discuss inversion strategies

Then, we will work with a synthetic example to
- demonstrate how to explore aspects of the physics with SimPEG
- explore the role and influence of parameters used in an inversion

## Prerequisites

**Software**

* Some knowledge of Python is assumed (for example, you might want to watch the
  [getting started with python](https://transform.softwareunderground.org/2022-getting-started-python) tutorial).
* All coding will be done in Jupyter notebooks. I'll explain how they work
  briefly but it will help if you've used them before.
* We'll use [numpy](https://numpy.org/), [matplotlib](https://matplotlib.org/), and
  [ipywidgets](https://ipywidgets.readthedocs.io/)
  You don't need to be an expert in these tools but some familiarity will help.

**Geophysical Inversions**

* This tutorial will focus on Direct Current (DC) Resistivity and Induced Polarization (IP).
  I'll explain the basic principles, but if these are new to you, then I would recommend
  taking a read through the [DC Resistivity](https://gpg.geosci.xyz/content/DC_resistivity/index.html)
  and [Induced Polarization](https://gpg.geosci.xyz/content/induced_polarization/index.html) sections
  of the [Geophysics for Practicing Geoscientists resource](https://gpg.geosci.xyz/index.html)
* Similarly, I do not assume an extensive background in inversions, but it will help if you have been
  introduced to some concepts. The [GIFTools Cookbook](https://giftoolscookbook.readthedocs.io/en/latest/content/fundamentals/index.html)
  provides a nice overview.

## Setup

There are a few things you'll need to follow the tutorial:

1. A working Python installation. I recommend using [Miniforge](https://github.com/conda-forge/miniforge), but you can also use [Anaconda](https://www.anaconda.com/download)
2. To install the [conda environment](./environment.yml) for this tutorial
3. A web browser that works with Jupyter
   (basically anything except Internet Explorer)

**Windows users:** If you ar using Anaconda, when you see "*terminal*" in the instructions,
this means the "*Anaconda Prompt*" program for you.

### Step 1: Python

Install Python on your machine. I recommend using [Miniforge](https://github.com/conda-forge/miniforge), but you can also use [Anaconda](https://www.anaconda.com/download)

If you are looking for tutorials, you can take a look at these videos:
for [Windows](https://youtu.be/FdatS_NKVrM)
and [Linux](https://youtu.be/3ncwbHyZeAg)

This will get you a working Python 3 installation with the `conda` package
manager. If you already have one, you can skip this step.

### Step 2: Download the SimPEG tutorials

To access the notebooks, there are 3 options (in order of preference):
1. Use git to clone this repository
2. You can use the `download` option to download this repository as a zip file from GitHub or using this link: https://github.com/ubcgif/2025-sustech-simpeg-tutorial/archive/refs/heads/main.zip. If you do this, follow all instructions below, replacing the `git clone` step with download and unzip the zip file with the repository contents.
3. You can run the notebooks online with binder through: https://mybinder.org/v2/gh/ubcgif/2025-sustech-simpeg-tutorial/main

To clone this repository, open up a terminal and navigate to where you want this repository stored on your computer.

Then run
```
git clone https://github.com/ubcgif/2025-sustech-simpeg-tutorial.git
```
to clone the repository, and `cd` into the `2025-sustech-simpeg-tutorial` directory
```
cd 2025-sustech-simpeg-tutorial
```

Alternatively, you can download the zip file of the tutorial contents, unzip those contents and open a
terminal in the `2025-sustech-simpeg-tutorial` directory that contains the tutorial contents.

### Step 3: Create the SimPEG tutorial conda environment

From inside of the `2025-sustech-simpeg-tutorial` repository, create the `2025-sustech-simpeg` conda environment
```
conda env create -f environment.yml
```
and activate the environment
```
conda activate 2025-sustech-simpeg
```

### Step 4: Launching the notebooks

Once you have activated the conda environment, you can launch the notebooks
```
jupyter lab
```
Jupyter will then launch in your web-browser.

## Resources

**Resources on SimPEG**
- [Docs](http://docs.simpeg.xyz/)
- [Mattermost chat](https://mattermost.softwareunderground.org/simpeg)

**Resources on Geophysics and Inversions**
- [Geophysics for Practicing Geoscientists](https://gpg.geosci.xyz/)
- [EM GeoSci](http://em.geosci.xyz/)
- Lectures from EOSC 350: Exploration & Environmental Geophysics ([2017](https://www.youtube.com/watch?v=C1U2okdfMbU&list=PLd9tNwsUm9jOhbLqjhjDW6ASqwRJtHTb5), [2018](https://www.youtube.com/watch?v=7kFPNooixyw&list=PLd9tNwsUm9jPrWrpdg1JHLieKrzK5w8_-))
- DISC 2017 lectures ([Mexico City](https://www.youtube.com/watch?v=uCnfWXWs5MM&list=PLd9tNwsUm9jM8GWLJm7XLLrE9PYuK-ca2))


## License

All code and text in this repository is free software: you can redistribute it and/or
modify it under the terms of the MIT License.
A copy of this license is provided in [LICENSE](LICENSE).
