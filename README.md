# Azure ML Designer: Predicting Building Heating Load for Energy Efficiency

## Project Overview
Built a complete regression pipeline in **Azure Machine Learning Designer** (low-code drag-and-drop interface) to predict **heating load** of buildings based on design parameters. Compared two models: Linear Regression vs. Decision Forest Regression.

- **Dataset**: [UCI Energy Efficiency Data Set](https://archive.ics.uci.edu/dataset/242/energy+efficiency)  
  - 768 building configurations (simulated in Ecotect)  
  - 8 input features + 2 targets (focused on Y1 Heating Load)  
  - No missing values  
  - Open-source (CC BY 4.0)  
  - Sample preview in `/data/sample_energy_efficiency.csv`

- **Features & Target**:

| Variable | Type       | Data Type  | Description                     |
|----------|------------|------------|---------------------------------|
| X1      | Feature   | Continuous | Relative Compactness           |
| X2      | Feature   | Continuous | Surface Area                   |
| X3      | Feature   | Continuous | Wall Area                      |
| X4      | Feature   | Continuous | Roof Area                      |
| X5      | Feature   | Continuous | Overall Height                 |
| X6      | Feature   | Integer    | Orientation                    |
| X7      | Feature   | Continuous | Glazing Area                   |
| X8      | Feature   | Integer    | Glazing Area Distribution      |
| Y1      | Target    | Continuous | Heating Load (kWh/m²)          |

- **Azure Workflow**:
  1. Uploaded dataset to Azure ML data assets.
  2. Selected columns in pipeline.
  3. Cleaned missing data (imputed with mean).
  4. Split data: 75% train / 25% test.
  5. Trained Linear Regression and Decision Forest Regression models.
  6. Scored predictions for both.
  7. Evaluated and compared performance.

- **Key Result**: **Decision Forest Regression significantly outperformed Linear Regression**, with much lower errors and near-perfect fit (R² 0.992).

## Visual Proof from Azure ML Designer

**Dataset Preview & Verification**  
![Energy Efficiency Data](images/energy_efficiency_data.png)

**Full Pipeline Canvas & Runtimes**  
![Pipeline and Runtimes](images/pipeline_and_runtimes.png)

**Model Architecture & Training Modules**  
![Model Architecture](images/model_architecture.png)

**Evaluation Metrics Comparison**  
![Evaluation Metrics](images/evaluation_metrics.png)

## Results Summary

| Metric                        | Linear Regression | Decision Forest Regression |
|-------------------------------|-------------------|----------------------------|
| Relative Absolute Error      | 0.132            | 0.051                     |
| Mean Absolute Error          | 0.748            | 0.289                     |
| Root Mean Squared Error      | 1.4              | 0.67                      |
| Coefficient of Determination (R²) | 0.967       | 0.992                     |

Decision Forest's superior performance shows ensembles handle non-linear building physics better—great insight for sustainable design.

## Learnings
- Designer enables fast prototyping and model comparison without coding.
- Data prep (imputation, splitting) and evaluation are seamless in one visual flow.
- Applied to real-world energy efficiency: Features like glazing and height strongly influence heating needs.
- Used free Azure credits for hands-on practice.

To replicate: In Azure ML Studio Designer, drag these modules, upload the UCI dataset, and run as shown.

MIT License – happy to have you reference or build on it!

Connect on X @Mvierhe1 for questions or feedback.
