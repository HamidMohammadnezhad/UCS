# UCS Prediction App
### Explainable Machine Learning for the Unconfined Compressive Strength Prediction of Stabilized Clayey Soils

## Overview

The **UCS Prediction App** is a web-based application developed using Streamlit to estimate the unconfined compressive strength (UCS) of stabilized clayey soils using a trained Gradient Boosting regression model.

Unconfined compressive strength is an important mechanical parameter in geotechnical engineering and soil stabilization. Its experimental determination can be time-consuming and resource-intensive, particularly when multiple soil properties, stabilizing additives, curing conditions, and environmental exposure conditions must be considered.

This application provides a user-friendly interface for obtaining rapid UCS estimates from user-defined input parameters. It is intended to support preliminary engineering assessments, research activities, and the evaluation of soil stabilization scenarios.

## Features

- **Machine learning-based prediction:** Estimates UCS using a trained Gradient Boosting regression model.
- **Multiple input parameters:** Accepts 20 input variables associated with soil characteristics, stabilization materials, and relevant treatment conditions.
- **Interactive web interface:** Enables users to obtain predictions without directly interacting with the underlying Python code.
- **Prediction visualization:** Presents the estimated UCS in kilopascals (kPa).
- **Input data inspection:** Allows users to review the parameters submitted for prediction.
- **Data export:** Supports downloading input data in CSV format.
- **Pre-trained model integration:** Uses serialized model and feature-name files for prediction.

## Repository Structure

```text
UCS/
├── app.py                # Streamlit application
├── ucs_model.pkl         # Trained Gradient Boosting model
├── feature_names.pkl     # Input feature names and ordering
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

## Methodology

The application uses a supervised machine learning regression approach to estimate UCS based on 20 input variables.

The prediction workflow consists of the following steps:

1. **Input specification:** The user provides values for the required input parameters.
2. **Input preparation:** The values are organized according to the feature names and ordering expected by the trained model.
3. **Model inference:** The pre-trained Gradient Boosting regressor processes the input data and generates a UCS estimate.
4. **Result presentation:** The predicted UCS is displayed in kPa, and the submitted input data can be reviewed and exported.

The model and feature names are stored separately to facilitate model loading and maintain the correspondence between the input variables and the trained estimator.

## Installation

### Prerequisites

- Python installed on your system
- pip package manager
- Git

Python 3.11 is a recommended starting point; the compatible version should be confirmed against the dependencies specified in `requirements.txt`.

### 1. Clone the repository

```bash
git clone https://github.com/HamidMohammadnezhad/UCS.git
cd UCS
```

### 2. Create a virtual environment

Creating a virtual environment is recommended to isolate the application's dependencies.

**Windows**

```bash
python -m venv .venv
.venv\Scripts\activate
```

**macOS/Linux**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Running the Application

After installing the dependencies, run the following command from the repository directory:

```bash
streamlit run app.py
```

Streamlit will start a local web server and display a URL, typically:

```text
http://localhost:8501
```

Open this URL in your web browser to access the application.

## How to Use

1. Launch the application using Streamlit.
2. Enter the values of the required input parameters.
3. Ensure that the input values and units are consistent with those used during model development.
4. Select the prediction control provided by the application.
5. Review the estimated UCS in kPa.
6. Inspect the submitted input parameters, if required.
7. Download the input data as a CSV file when needed.

**Important:** Default input values are provided for interface initialization only and should not be interpreted as recommended engineering values. Replace them with appropriate values before generating a prediction.

## Model Files

The application requires the following serialized files:

| File | Description |
|---|---|
| `ucs_model.pkl` | Contains the trained Gradient Boosting regression model. |
| `feature_names.pkl` | Contains the input feature names and their expected ordering. |

Both files must be available in the application directory. The model should be loaded using a compatible Python environment and the same preprocessing assumptions used during training.

Only load serialized pickle files from trusted sources, as loading untrusted pickle files can execute malicious code.

## Intended Applications

The application may be used to support:

- Preliminary estimation of the UCS of stabilized clayey soils.
- Research into the influence of soil properties and stabilization variables on strength.
- Comparison of candidate stabilization scenarios within the model's applicable domain.
- Preliminary evaluation of soil stabilization mix designs.
- Identification of cases for which additional laboratory testing may be warranted.

The application is intended as a research and decision-support tool rather than a replacement for standardized laboratory testing or professional engineering judgment.

## Limitations

- Prediction reliability depends on the quality, size, and representativeness of the training dataset.
- Predictions may be less reliable for input combinations or material conditions that differ substantially from those represented in the training data.
- The application does not independently verify the physical plausibility of every user-entered value.
- Results should be interpreted within the scope of the model's training data and validation results.
- Predictions should not be treated as experimentally verified measurements.
- The application is not intended to provide independent certification of soil properties or replace required geotechnical investigations.

For engineering applications, predicted values should be evaluated alongside relevant experimental evidence, applicable design standards, and professional engineering judgment.

## Reproducibility

The repository provides the trained model and its associated feature-name file for prediction.

Reproducing the original model-development process requires additional information, including the original dataset, data preprocessing procedures, hyperparameter optimization configuration, validation strategy, and software environment.

For reproducible research, these details should be documented in the associated scientific publication or supplementary materials.

## Acknowledgments

This application was developed in connection with research activities in geotechnical engineering and machine learning-based prediction of soil properties.

**Affiliation:** Faculty of Civil, Water and Environmental Engineering, Shahid Beheshti University.

## Citation

If this application is used in academic research, please cite the associated scientific publication when its bibliographic details become available.

Repository: [UCS Prediction App on GitHub](https://github.com/HamidMohammadnezhad/UCS)

## License

No software license is currently specified in this repository. Unless a license is added, reuse, modification, and redistribution remain subject to applicable copyright law. Please contact the repository owner regarding permissions.

---

**Disclaimer:** The predictions generated by this application are intended for preliminary research and decision support. They should not be used as the sole basis for design, construction, or safety-critical engineering decisions.

---

*Faculty of Civil, Water and Environmental Engineering, Shahid Beheshti University*

**Copyright © 2026 Dr. Mohammadnezhad Research Team. All rights reserved.**
