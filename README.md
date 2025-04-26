# Deep Cox Mixtures for Survival Regression - Reproduction Study (CS598: Deep Learning for Healthcare @ UIUC)

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This repository contains our reproduction study of the paper ["Deep Cox Mixtures for Survival Regression"](https://arxiv.org/abs/2101.06536) by Nagpal et al. (2021), including our full analysis paper [Revisit_DeepCoxMixturesForSurvivalRegression.pdf](Revisit_DeepCoxMixturesForSurvivalRegression.pdf).

## Table of Contents
- [Project Overview](#project-overview)
- [Key Features](#key-features)
- [Datasets](#datasets)
- [Notebooks](#notebooks)
- [Results](#results)
- [Dataset Analysis](#dataset-analysis)
- [Contributors](#contributors)
- [License](#license)
- [Acknowledgments](#acknowledgments)

## Project Overview

Survival analysis predicts the probability of an event occurring within a specific time period, with applications ranging from medical prognosis to industrial reliability. This project focuses on reproducing and evaluating the Deep Cox Mixtures (DCM) model, which addresses limitations of traditional survival analysis methods like the Cox Proportional Hazards model.

## Key Features

### Implementation Highlights
- Press-to-run Colab Notebooks for easy reproduction
- Additional GBSG dataset for verification
- Comprehensive dataset exploration and visualization
- Multiple evaluation metrics comparison

### Evaluation Metrics
| Metric | Description | Ideal Value |
|--------|------------|------------|
| C-index | Ranking accuracy | Closer to 1.0 |
| Brier Score | Prediction calibration | Closer to 0.0 |
| ECE | Calibration error | Closer to 0.0 |
| AUC | Discrimination | Closer to 1.0 |

## Datasets

### SUPPORT Dataset
- ​**Source**: Study to Understand Prognoses Preferences Outcomes and Risks of Treatment
- ​**Size**: 9,105 critically ill patients
- ​**Features**: 25 clinical/demographic variables
- ​**Task**: Predict 180-day survival probability
- ​**Access**: [Kaggle](https://www.kaggle.com/datasets/joebeachcapital/support2)

### SEER Dataset
- ​**Source**: National Cancer Institute's registry
- ​**Size**: ~400,000 breast cancer cases (subset used)
- ​**Features**: Tumor characteristics, treatment, demographics
- ​**Task**: Predict cancer-specific survival
- ​**Access**: [Kaggle](https://www.kaggle.com/datasets/sujithmandala/seer-breast-cancer-data)

### GBSG Dataset
- ​**Source**: German Breast Cancer Study Group
- ​**Size**: 686 patients with node-positive breast cancer
- ​**Features**: Tumor characteristics and treatment data
- ​**Task**: Predict recurrence-free survival
- ​**Access**: [Kaggle](https://www.kaggle.com/datasets/utkarshx27/breast-cancer-dataset-used-royston-and-altman)

## Notebooks

| Notebook | Description | Colab |
|----------|-------------|-------|
| [SEER Analysis](598DL4H_DCM_CV_Example_Code_SEER.ipynb) | Cancer survival modeling | [![Open](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/blob/main/598DL4H_DCM_CV_Example_Code_SEER.ipynb) |
| [SUPPORT Analysis](598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb) | ICU patient survival | [![Open](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/blob/main/598DL4H_DCM_CV_Example_Code_SUPPORT.ipynb) |
| [GBSG Analysis](598DL4H_DCM_CV_Example_Code_GBSG.ipynb) | Breast cancer survival | [![Open](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/blob/main/598DL4H_DCM_CV_Example_Code_GBSG.ipynb) |

## Results

### Performance Comparison

​**SUPPORT Dataset Results (75th Percentile)​**​

| Model       | AUC   | C-index | ECE   | Brier Score |
|-------------|-------|---------|-------|-------------|
| CPH         | 0.739 | 0.666   | 0.040 | 0.197       |
| DCM (Ours)  | 0.716 | 0.650   | 0.079 | 0.211       |
| DCM (Paper) | 0.726 | 0.675   | 0.026 | 0.212       |

​**SEER Dataset Results (75th Percentile)​**​

| Model       | AUC   | C-index | ECE   | Brier Score |
|-------------|-------|---------|-------|-------------|
| CPH         | 0.738 | 0.730   | 0.036 | 0.132       |
| DCM (Ours)  | 0.750 | 0.736   | 0.048 | 0.129       |
| DCM (Paper) | 0.855 | 0.827   | 0.010 | 0.106       |

​**GBSG Dataset Results (75th Percentile)​**​

| Model | CTD  | ECE  |
|-------|---------|---------|
| CPH   | 0.554   | 0.219   |
| DCM   | 0.669   | 0.295   |
| DSM   | 0.669   | 0.315   |
| RSF   | 0.669   | 0.219   |

## Dataset Analysis

| Notebook | Description | Colab |
|----------|-------------|-------|
| [SEER Analysis](598DL4H_DCM_CV_Example_Code_SEER_Analysis.ipynb) | Feature analysis | [![Open](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/blob/main/598DL4H_DCM_CV_Example_Code_SEER_Analysis.ipynb) |
| [SUPPORT Analysis](598DL4H_DCM_CV_Example_Code_SUPPORT_Analysis.ipynb) | Data exploration | [![Open](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/chrisyu-uiuc/revisit-deepcoxmixtures-cs598-uiuc/blob/main/598DL4H_DCM_CV_Example_Code_SUPPORT_Analysis.ipynb) |

## Contributors

- ​**Chris Yu**​ ([hmyu2@illinois.edu](mailto:hmyu2@illinois.edu))
- ​**Jimmy Lee**​ ([jl279@illinois.edu](mailto:jl279@illinois.edu))

## License

MIT License - See [LICENSE](LICENSE) for details.

## Acknowledgments

- Original DCM authors: Chirag Nagpal et al.
- Course: [CS598: Deep Learning for Healthcare](https://sunlab.org/) @ UIUC
- Dataset providers: SUPPORT Study Group, NCI SEER Program, GBSG