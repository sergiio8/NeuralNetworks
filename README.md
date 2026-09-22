# Wine Quality Prediction with Scikit-learn

Academic machine-learning coursework deliverable developed by Sergio Martínez Olivera and [Daniel Roldán Serrano](https://github.com/danirold).

## Overview

This repository studies wine-quality prediction from physicochemical measurements in the Portuguese *Vinho Verde* wine-quality dataset. The notebook uses Python and scikit-learn to explore the data, normalize selected features, compare k-nearest-neighbors baselines, train multilayer perceptrons, and evaluate predictions with cross-validation.

The project is intended as an educational model-comparison exercise, not as a production application or deployed prediction service.

## Dataset

The included `calidad_vinos.csv` file contains 1,599 wine samples with 11 physicochemical input variables and a `quality` target:

- fixed acidity
- volatile acidity
- citric acid
- residual sugar
- chlorides
- free sulfur dioxide
- total sulfur dioxide
- density
- pH
- sulphates
- alcohol

The notebook identifies the dataset as the UCI Wine Quality dataset and models quality scores ranging from 0 to 10. The observed data contains quality labels from 3 through 8, with classes 5 and 6 substantially more frequent than the others.

## Methods

`NNSergio_Daniel.ipynb` contains the complete analysis:

1. Exploratory data inspection and Pearson-correlation-based feature selection
2. Feature standardization
3. k-nearest-neighbors baseline models with cross-validated mean squared error
4. Multilayer perceptron models with regularization-parameter exploration
5. Cross-validated error analysis and classification-style metrics
6. Error-distribution and per-quality analysis

## Reported results

The saved notebook outputs report:

| Metric | Result |
| --- | ---: |
| MSE | 0.41596 |
| MAE | 0.49896 |
| R² | 0.36179 |
| Accuracy | 0.82 |
| Weighted average F1 | 0.81 |
| Macro average F1 | 0.43 |

The weighted metrics are substantially higher than macro F1 because the dataset is imbalanced. The results therefore indicate stronger performance on common quality levels than on rare classes; the reported accuracy should not be presented as an unqualified F1 score.

## Reproducing the notebook

1. Create and activate a Python environment.
2. Install the dependencies:

   ```bash
   python -m pip install -r requirements.txt
   ```

3. Launch Jupyter:

   ```bash
   jupyter notebook
   ```

4. Open `NNSergio_Daniel.ipynb` and run the cells in order from the repository root so that `calidad_vinos.csv` is found.

## Repository contents

| File | Description |
| --- | --- |
| `NNSergio_Daniel.ipynb` | Coursework analysis and model evaluation |
| `calidad_vinos.csv` | Wine-quality dataset used by the notebook |
| `requirements.txt` | Python dependencies required to run the notebook |
| `LICENSE` | Repository license |

## Limitations

This is a coursework experiment rather than a production-ready model. The dataset is imbalanced, the macro F1 score is notably lower than the weighted F1 score, and the notebook does not provide a deployment interface, monitoring, or a production pipeline. Results should be interpreted in the context of the supplied dataset and notebook workflow.
