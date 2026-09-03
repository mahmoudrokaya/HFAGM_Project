# `.venv_sklearn152`

## Overview

The `.venv_sklearn152` folder is a local Python virtual environment used to run the HFAGM_Project code with a controlled software configuration.

Its primary purpose is to isolate the project dependencies from the system-wide Python installation and from other Python projects on the same machine.

The folder name indicates that this environment was created specifically for experiments requiring a scikit-learn 1.5.2 compatible setup.

---

## Purpose

This virtual environment is used to provide a reproducible local execution environment for the machine-learning experiments implemented under `New_Code`.

It may contain packages required for:

- data preprocessing;
- model training;
- repeated stratified holdout evaluation;
- predictive performance calculation;
- class-balancing experiments;
- subgroup fairness analysis;
- predictor-level analysis;
- statistical processing;
- generation of tables and figures.

Using a dedicated virtual environment helps prevent package-version conflicts and makes it easier to reproduce the experimental workflow.

---

## Important Note

This folder is a **local development environment** and should normally **not be uploaded to GitHub**.

Virtual environments contain installed Python packages, compiled binaries, temporary files, interpreter-specific files, and machine-dependent paths. They can also become very large.

The environment should therefore be excluded through `.gitignore`.

Recommended entry:

```gitignore
.venv_sklearn152/
