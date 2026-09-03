# HFAGM_Project

## Leakage-Safe and Fairness-Aware Clinical Machine Learning Evaluation Framework

HFAGM_Project is a research-oriented clinical machine learning project for the rigorous evaluation of predictive models using structured healthcare data. The project emphasizes **leakage-safe model development, repeated-partition robustness, class-balancing assessment, subgroup fairness, predictor-level discrimination, and temporal interpretability**.

Rather than relying on a single headline performance metric, HFAGM_Project evaluates predictive performance from several complementary perspectives. The framework is designed to distinguish strong retrospective discrimination from evidence required for prospective clinical validity.

---

## 1. Project Overview

Machine learning models applied to clinical datasets can achieve apparently excellent predictive performance while remaining vulnerable to methodological problems such as:

- information leakage between training and test data;
- dependence on a favorable train–test partition;
- inappropriate handling of class imbalance;
- demographic differences in model behavior;
- highly predictive individual variables that dominate model performance;
- uncertain temporal availability of clinical predictors;
- overinterpretation of retrospective results as prospective clinical evidence.

HFAGM_Project addresses these issues through an integrated evaluation workflow.

The framework evaluates:

1. **Leakage-safe predictive performance**
2. **Stability across repeated stratified holdouts**
3. **The effect of training-only class balancing**
4. **Group fairness across available sensitive attributes**
5. **Individual predictor discrimination**
6. **Predictor chronology and temporal interpretability**

The objective is not simply to maximize predictive performance, but to determine **what the observed performance actually supports**.

---

## 2. Clinical Dataset

The current evaluation uses a retrospective structured clinical dataset containing:

- **193 patients**
- **51 predictors**
- **100 recovered/surviving patients**
- **93 deceased patients**

The binary outcome is encoded as:

- `0` — Recovered/Survived
- `1` — Deceased

The dataset contains demographic and clinical variables, including laboratory measurements and other structured patient characteristics.

The analysis is retrospective. Consequently, the reported results describe discrimination within the available cohort and should not be interpreted automatically as evidence of prospective clinical performance.

---

## 3. Evaluation Philosophy

HFAGM_Project follows a central principle:

> **High predictive performance alone is insufficient evidence of a reliable clinical prediction system.**

A model should instead be evaluated across multiple dimensions.

The framework therefore separates:

**Predictive discrimination**

How accurately does the model distinguish the clinical outcomes?

**Internal robustness**

Does performance remain stable when the patient cohort is partitioned differently?

**Class-balancing sensitivity**

Does modifying the class distribution of the training data actually improve prediction?

**Group fairness**

Does model behavior differ according to available sensitive demographic attributes?

**Predictor informativeness**

Are individual clinical variables already highly discriminative?

**Temporal validity**

Would the predictors have been available at the intended time of prediction?

These dimensions are analyzed separately before being integrated into the final interpretation.

---

## 4. Leakage-Safe Evaluation

A major methodological requirement of the project is strict separation between training and test data.

The workflow follows the general sequence:

```text
Original Patient Dataset
        |
        v
Stratified Train/Test Split
        |
        +-----------------------+
        |                       |
        v                       v
   Training Data            Test Data
        |
        v
Fit Preprocessing
on Training Data Only
        |
        v
Transform Training Data
        |
        +-----------------------> Transform Test Data
        |
        v
Optional Training-Only
Class Balancing
        |
        v
Model Training
        |
        v
Evaluation on Untouched
Test Observations
