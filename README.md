# UCS Prediction App
### Machine Learning-Based Prediction of the Unconfined Compressive Strength of Stabilized Clayey Soils

## Overview

The **UCS Prediction App** is a web-based application developed using Streamlit to estimate the unconfined compressive strength (UCS) of stabilized clayey soils using a trained Gradient Boosting regression model.

Unconfined compressive strength is an important parameter in geotechnical engineering, particularly for evaluating the mechanical performance of stabilized soils. Its laboratory determination can require considerable time and resources when multiple soil properties, stabilizing additives, and curing conditions are involved.

This application provides a convenient interface for obtaining rapid UCS estimates from user-defined input parameters. It is intended to support preliminary engineering assessments, research activities, and the evaluation of soil stabilization scenarios.

## Key Features

- **Machine learning prediction:** Estimates UCS using a trained Gradient Boosting regression model.
- **Twenty input parameters:** Accepts the soil and stabilization-related variables required by the model.
- **Interactive web interface:** Allows users to enter input values and obtain predictions without directly interacting with the underlying Python code.
- **Prediction results:** Reports the estimated UCS in kilopascals (kPa).
- **Input data inspection:** Displays the parameters submitted for prediction.
- **Data export:** Allows users to download the entered input parameters as a CSV file.
- **Pre-trained model integration:** Loads the trained model and its corresponding feature names from serialized files.

## Repository Structure

```text
UCS/
├── app.py                # Streamlit application
├── ucs_model.pkl         # Trained machine learning model
├── feature_names.pkl     # Model input feature names
├── requirements.txt      # Python dependencies
└── README.md             # Project documentation
```

## Methodology

The application uses a supervised machine learning regression approach to estimate UCS from twenty input variables.

The prediction workflow consists of the following steps:

1. **Input specification:** The user provides the values of the required input parameters.
2. **Data preparation:** The inputs are arranged in a structured format using the feature names associated with the trained model.
3. **Model inference:** The pre-trained Gradient Boosting model generates a UCS estimate.
4. **Result presentation:** The predicted UCS is displayed in kPa, and the submitted input data can be inspected and exported.

The model and feature-name definitions are stored separately to facilitate model loading and preserve the correspondence between input variables and the trained estimator.

## Installation

### Prerequisites

- Python 3.10 or a compatible Python version supported by the dependencies
- pip package manager
- Git

### 1. Clone the repository

```bash
git clone https://github.com/HamidMohammadnezhad/UCS.git
cd UCS
```

### 2. Create a virtual environment (recommended)

```bash
python -m venv .venv
```

Activate the environment:

**Windows**

```bash
.venv\Scripts\activate
```

**macOS/Linux**

```bash
source .venv/bin/activate
```

### 3. Install the dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

## Running the Application

From the repository directory, execute:

```bash
streamlit run app.py
```

Streamlit will start a local web server and provide a URL, typically:

```text
http://localhost:8501
```

Open the displayed URL in a web browser to access the application.

## How to Use

1. Launch the application.
2. Enter the values of the twenty required input parameters.
3. Check that the values and their units are consistent with the model's training data.
4. Select **Predict UCS**.
5. Review the estimated unconfined compressive strength in kPa.
6. Expand the input-data section to inspect the submitted values.
7. Download the input data as a CSV file if required.

**Important:** The reliability of a prediction depends on the quality of the input data and the extent to which the selected conditions are represented in the model's training dataset.

## Model Files

The application requires the following serialized files:

| File | Description |
|---|---|
| `ucs_model.pkl` | Contains the trained Gradient Boosting regression model. |
| `feature_names.pkl` | Contains the input feature names and their expected ordering. |

Both files must be available in the application directory. The model should be loaded with a compatible software environment and the same preprocessing assumptions used during training.

## Intended Applications

The application may be useful for:

- Preliminary estimation of the UCS of stabilized clayey soils.
- Research into the effects of soil properties and stabilization variables on strength.
- Comparing candidate soil stabilization scenarios within the model's applicable domain.
- Supporting preliminary mix-design investigations and identifying cases that may require further laboratory testing.

The application is intended as a research and decision-support tool rather than a replacement for standardized laboratory testing or professional engineering judgment.

## Limitations

- Predictions are subject to the limitations and representativeness of the training dataset.
- Reliability may decrease for input combinations or material conditions that differ substantially from those represented during model development.
- The application does not independently verify the physical plausibility of every user-entered value.
- Predictions should be interpreted within the scope of the model's training data and validation results.
- The application is not intended to provide independent certification of soil properties or replace required geotechnical investigations.

## Reproducibility

The repository includes the trained estimator and the associated feature-name file required for inference. Reproducing the original model-development process additionally requires the relevant dataset, preprocessing procedures, training configuration, and evaluation protocol.

For reproducible research, the software environment and model-development details should be documented alongside the associated scientific publication.

## Acknowledgments

This application was developed for research in geotechnical engineering and machine learning-based prediction of soil properties.

Repository: [HamidMohammadnezhad/UCS](https://github.com/HamidMohammadnezhad/UCS)

## Citation

If this application is used in academic research, please cite the associated scientific publication when its bibliographic details become available.

## License

No license is specified in this repository at present. Unless a license is added, reuse and redistribution remain subject to applicable copyright law. Please contact the repository maintainer regarding permissions.

---

**Disclaimer:** The predictions generated by this application are intended for preliminary research and decision support. They should not be used as the sole basis for design, construction, or safety-critical engineering decisions.
