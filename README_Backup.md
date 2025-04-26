# Deep Cox Mixtures for Survival Regression - Reproduction Study

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/)

This repository contains our reproduction study of the paper ["Deep Cox Mixtures for Survival Regression"](https://arxiv.org/abs/2101.06536) by Nagpal et al. (2021), including our full analysis paper [Revisit_DeepCoxMixturesForSurvivalRegression.pdf](Revisit_DeepCoxMixturesForSurvivalRegression.pdf).

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Datasets](#datasets)
- [Installation](#installation)
- [Usage](#usage)
- [Results](#results)
- [Contributors](#contributors)
- [License](#license)

## Project Overview

Survival analysis predicts the probability of an event occurring within a specific time period, with applications ranging from medical prognosis to industrial reliability. This project focuses on reproducing and evaluating the Deep Cox Mixtures (DCM) model, which addresses limitations of traditional survival analysis methods like the Cox Proportional Hazards model.

## Key Features

- Implementation of Deep Cox Mixtures model with:
  - Neural network feature encoding
  - Mixture modeling framework
  - Non-parametric baseline survival estimation
- Comprehensive analysis notebooks:
  - [DCM SEER Notebook](598DL4H_DCM_CV_Example_Code_SEER.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SEER.ipynb)
  - [DCM SUPPORT Notebook](598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb)
- Evaluation metrics including:
  - Concordance Index (C-index)
  - Brier Score
  - Expected Calibration Error (ECE)
  - Time-dependent AUC

## Datasets

### SUPPORT Dataset
- Contains records of 9,105 critically ill patients
- Features: Demographic, clinical, and laboratory measurements
- Prediction task: 180-day survival probability

### SEER Dataset
- Comprehensive cancer statistics from US population
- Features: Tumor characteristics, treatment, demographics
- Prediction task: Cancer survival probabilities

## Installation

1. Clone this repository:
```bash
git clone https://github.com/chrisyu-uiuc/cs598dl4h-deepcoxmixtures.git
cd cs598dl4h-deepcoxmixtures
pip install -r requirements.txt
```
## Usage

The analysis is performed through our interactive Jupyter notebooks:

- [DCM SEER Notebook](598DL4H_DCM_CV_Example_Code_SEER.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SEER.ipynb)
- [DCM SUPPORT Notebook](598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb)

Adjustable parameters are available in each notebook's configuration section.

## Results Summary

### SUPPORT Dataset Performance

| Model       | AUC   | C-index | ECE   | Brier Score |
|-------------|-------|---------|-------|-------------|
| CPH         | 0.739 | 0.666   | 0.040 | 0.197       |
| DCM (Ours)  | 0.716 | 0.650   | 0.079 | 0.211       |
| DCM (Paper) | 0.726 | 0.675   | 0.026 | 0.212       |

### SEER Dataset Performance

| Model       | AUC   | C-index | ECE   | Brier Score |
|-------------|-------|---------|-------|-------------|
| CPH         | 0.738 | 0.730   | 0.036 | 0.132       |
| DCM (Ours)  | 0.750 | 0.736   | 0.048 | 0.129       |
| DCM (Paper) | 0.855 | 0.827   | 0.010 | 0.106       |

## Dataset Analysis


- [SEER Dataset Analysis Notebook](598DL4H_DCM_CV_Example_Code_SEER_Analysis.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SEER_Analysis.ipynb)
- [SUPPORT Dataset Analysis Notebook](598DL4H_DCM_CV_Example_Code_SUPPORT_Analysis.ipynb) [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/cs598dl4h-deepcoxmixtures/blob/main/598DL4H_DCM_CV_Example_Code_SUPPORT_Analysis.ipynb)


## Team

- ​**Chris Yu**​ ([hmyu2@illinois.edu](mailto:hmyu2@illinois.edu))
- ​**Jimmy Lee**​ ([jl279@illinois.edu](mailto:jl279@illinois.edu))

## License

MIT License - See [LICENSE](LICENSE) for details.