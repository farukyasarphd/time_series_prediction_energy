# Time Series Prediction of Appliances Energy Consumption

In this project I build a machine learning model to predict energy consumption using a multivariate time series dataset. The main goal is to develop a robust model that can forecast energy usage for future periods where regressors (sensor data) is not available.

---

## Dataset

**Dataset Name**: Appliances Energy Prediction Dataset\
**Source**: UCI Machine Learning Repository\
**Description**:

- The dataset contains measurements of energy consumption in a household collected over time.
- It includes temperature and humidity conditions recorded at various locations within the house.
- The target variable is the total energy consumed by appliances.

**Key Features**:

- `Appliances`: Energy consumption (target variable).
- Environmental conditions: Temperature, humidity, pressure.
- Time-based features: Date and time.

---

## Environment Setup

### 1. Clone the Repository

```bash
git clone https://github.com/farukyasarphd/time_series_prediction_energy.git
cd time_series_prediction_energy
```

### 2. Install Dependencies with Poetry

```bash
poetry install
poetry shell
```

### 3. Export Dependencies (Optional)

```bash
poetry export --format=requirements.txt --output=requirements.txt
```

---

## Project Structure

```
📦 appliances-energy-prediction
┣ 📂 data            # Raw and processed data
┣ 📂 notebooks       # Jupyter notebooks for EDA and modeling
┣ 📂 src             # Python scripts and modules
┃ ┣ 📂 utils         # Helper functions
┃ ┗ 📜 __init__.py   # Package marker
┣ 📂 models          # Model training and evaluation scripts
┣ 📂 reports         # Documentation and visualizations
┣ 📜 README.md       # Project overview
┣ 📜 pyproject.toml  # Poetry configuration
┣ 📜 requirements.txt # Exported dependencies
┗ 📜 .gitignore       # Ignored files
```

---

## Running Scripts and Notebooks

1. Start Jupyter Notebook:

```bash
poetry run jupyter notebook
```

2. Open the `notebooks/` folder and run the exploratory data analysis (EDA) notebook.
3. Train and evaluate models using scripts inside the `src/` and `models/` folders.

---

## Contact

Author: Faruk Yaşar\
GitHub: [farukyasarphd](https://github.com/farukyasarphd)

