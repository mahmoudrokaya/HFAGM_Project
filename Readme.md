# Data

## Overview

The raw patient-level dataset used in HFAGM_Project is **not redistributed through this GitHub repository**.

This repository contains the source code, experiment definitions, and reproducibility workflow required to process and evaluate the data. Researchers wishing to reproduce the experiments should obtain the original dataset from its external source and place it locally in the `data/` directory as described below.

The decision not to redistribute the dataset through GitHub preserves the original dataset provenance, avoids unnecessary duplication, and ensures that users obtain the data under the terms and conditions defined by the original data provider.

---

## Dataset Used in the Study

The experiments reported in HFAGM_Project use a retrospective structured clinical dataset for binary clinical-outcome prediction.

### Dataset characteristics

| Property | Description |
|---|---|
| Data type | Structured/tabular clinical data |
| Number of patients | 193 |
| Number of model predictors | 51 |
| Clinical outcome | Recovery/survival versus death |
| Recovered/surviving patients | 100 |
| Deceased patients | 93 |
| Study design | Retrospective |
| Data collection period | March 2020 – February 2021 |
| Study location | King Faisal Hospital, Taif, Saudi Arabia |
| Prediction task | Binary clinical-outcome classification |

The outcome representation used by the project is:

```text
0 = Recovered / Survived
1 = Deceased
