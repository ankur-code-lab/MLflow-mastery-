# MLflow Mastery

A dedicated workspace for learning and mastering [MLflow](https://mlflow.org/), focusing on experiment tracking, model lifecycle management, and integration with classical machine learning models (like scikit-learn).

## Project Structure

This repository is organized into specific use cases and tracking scenarios:

- **`LogisticRegression_tracking/`**
  - Contains introductory examples (`1_getting_started.ipynb`) demonstrating MLflow tracking with Logistic Regression models for classification tasks.
- **`HousePricePrediction_tracking/`**
  - Explores tracking for a regression problem (`1_houseprice.ipynb`), demonstrating how to log metrics, parameters, and models when predicting house prices.

## Prerequisites

This project uses `uv` for fast Python package and dependency management.

- Python 3.11 or higher
- [uv](https://github.com/astral-sh/uv) (for dependency management)

## Installation & Setup

1. **Navigate to the workspace**:
   ```bash
   cd mlflow_mastery
   ```

2. **Install dependencies**:
   Use `uv` to create a virtual environment and install dependencies defined in `pyproject.toml`.
   ```bash
   uv sync
   ```

3. **Activate the virtual environment**:
   ```bash
   source .venv/bin/activate
   ```

## Usage

1. **Start the MLflow Tracking Server**:
   To view your experiments, metrics, and models in a web browser, start the MLflow UI. The project is configured to use a local SQLite database (`mlflow.db`) and a local `mlartifacts/` directory.
   ```bash
   mlflow ui --backend-store-uri sqlite:///mlflow.db --default-artifact-root ./mlartifacts
   ```
   *The MLflow UI will be accessible at [http://127.0.0.1:5000](http://127.0.0.1:5000).*

2. **Run the Notebooks**:
   Start Jupyter to execute the experiments:
   ```bash
   jupyter notebook
   ```
   Navigate to the respective tracking folders and run the notebooks to see MLflow in action!

## Configuration Notes

To maintain a clean version control history, the following files and directories are intentionally ignored by Git:
- **`mlflow.db`**: The SQLite backend store for MLflow tracking.
- **`mlartifacts/` & `mlruns/`**: Directories where MLflow saves model artifacts and logs.
- **`.env`**: Environment-specific configurations.
- **`uv.lock`**: The dependency lockfile.
