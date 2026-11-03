# Flight Delay Prediction Using Fuzzy Logic and Genetic Algorithm

## Project Overview

Flight delays are a major challenge in the aviation industry, affecting passengers, airline operations, and airport scheduling.

This project develops an intelligent flight delay prediction system using **Fuzzy Logic** and **Genetic Algorithm (GA)** optimization.

Fuzzy Logic estimates flight delay risk using predefined rules and membership functions, while the Genetic Algorithm optimizes selected fuzzy system parameters to improve prediction performance.

## Objectives

- Predict flight delays using Soft Computing techniques.
- Apply Fuzzy Logic to handle uncertain flight-related conditions.
- Optimize fuzzy system parameters using a Genetic Algorithm.
- Compare baseline and GA-tuned model performance.
- Evaluate models using classification metrics.

##  Dataset

**Source:** Hugging Face – `Algo0o/flight_delay`

**Target Variable:** `DEP_DEL15`

| Value | Description |
|---|---|
| 0 | Flight not delayed |
| 1 | Flight delayed by 15 minutes or more |

### Input Features

- Scheduled Departure Hour
- Flight Distance
- Day of the Week
- Month

## ⚙️ Technologies Used

| Technology | Purpose |
|---|---|
| Python | Programming language |
| Pandas | Data preprocessing |
| NumPy | Numerical operations |
| Scikit-fuzzy | Fuzzy inference system |
| Scikit-learn | Model evaluation |
| Matplotlib | Visualization |
| Seaborn | Statistical visualization |
| Hugging Face Datasets | Dataset loading |

## 🧠 Methodology

### 1. Data Preprocessing
- Load the flight delay dataset.
- Handle missing and invalid values.
- Extract departure hour, day, and month.
- Normalize numerical features.

### 2. Fuzzy Logic Model

The fuzzy inference system uses four input features with linguistic membership categories:

- Low
- Medium
- High

IF–THEN rules are applied to estimate a flight delay risk score.

### 3. Genetic Algorithm Optimization

The Genetic Algorithm optimizes:

- Membership function boundary.
- Classification threshold.

The optimization process includes:

1. Population initialization.
2. Fitness evaluation.
3. Selection.
4. Crossover.
5. Mutation.
6. Selection of the best-performing solution.

The F1-score on validation data is used as the fitness function.

### 4. Model Evaluation

The baseline Fuzzy Logic model is compared with the GA-tuned Fuzzy Logic model using accuracy, precision, recall, and F1-score.

## Results & Performance Analysis

### Model Comparison

| Evaluation Metric | Fuzzy Logic | GA-Tuned Fuzzy Logic |
|---|---:|---:|
| Accuracy | 74.40% | 68.60% |
| Precision | 40.00% | 35.51% |
| Recall | 3.17% | 30.16% |
| F1-score | 5.88% | 32.62% |

### Key Observations

- Recall improved from **3.17% to 30.16%**.
- F1-score increased from **5.88% to 32.62%**.
- Accuracy decreased from 74.40% to 68.60%.
- Precision decreased slightly from 40.00% to 35.51%.
- GA optimization improved the model's ability to identify delayed flights.

The results demonstrate that accuracy alone is not sufficient to evaluate flight delay prediction, particularly when identifying delayed flights is important.

##  Project Visualizations

The project includes visualizations of:

- Flight delay distribution.
- Genetic Algorithm optimization progress.
- GA-tuned Fuzzy Logic model.
- Model performance comparison.
- Confusion matrix.

## Installation and Execution

### Step 1: Clone the Repository

```bash
git clone https://github.com/sadhusravya123/flight-delay-prediction-fuzzy-ga.git
```

### Step 2: Navigate to the Project

```bash
cd flight-delay-prediction-fuzzy-ga
```

### Step 3: Install Dependencies

```bash
pip install datasets scikit-fuzzy scikit-learn pandas numpy matplotlib seaborn
```

### Step 4: Run the Notebook

Open the Jupyter Notebook:

```bash
jupyter notebook
```

Run the notebook cells sequentially to load the dataset, preprocess the data, train the fuzzy system, perform GA optimization, and evaluate the models.

##  Future Enhancements

- Incorporate weather conditions and airport congestion data.
- Improve fuzzy membership functions and rule coverage.
- Compare performance with Random Forest and Logistic Regression.
- Integrate real-time flight information.
- Develop a web-based flight delay prediction application.

## Conclusion

This project demonstrates how Fuzzy Logic and Genetic Algorithm optimization can be combined for flight delay prediction.

The GA-tuned model achieved significant improvements in recall and F1-score compared with the baseline model. Although accuracy decreased, the optimized model identified a greater proportion of delayed flights.

Further improvements in feature selection, fuzzy rule design, and optimization are required before practical deployment.


---

⭐ If you find this project interesting, consider giving the repository a star!
