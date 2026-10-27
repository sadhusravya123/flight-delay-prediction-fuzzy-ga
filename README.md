# Flight Delay Prediction Using Fuzzy Logic and Genetic Algorithm

## Project Overview

This project predicts whether a flight's departure delay will be **15 minutes or more** using Soft Computing techniques: Fuzzy Logic and a Genetic Algorithm (GA).

Fuzzy Logic estimates flight delay risk using membership functions and IF–THEN rules. The Genetic Algorithm optimizes selected fuzzy-system parameters to improve classification performance.

##  Objectives

- Predict flight departure delays using flight-related features.
- Implement a Fuzzy Logic inference system.
- Optimize fuzzy parameters using a Genetic Algorithm.
- Compare model performance using standard evaluation metrics.
- Visualize the results using tables and graphs.

##  Dataset

- **Source:** [Hugging Face — Flight Delay Dataset](https://huggingface.co/datasets/Algo0o/flight_delay)
- **Dataset ID:** `Algo0o/flight_delay`
- **Records:** Up to 100,000 records are sampled.
- **Access:** Public dataset; no Kaggle API key required.

### Features Used

| Feature | Description |
|---|---|
| `CRS_DEP_TIME` | Scheduled departure time |
| `DISTANCE` | Distance between airports |
| `FL_DATE` | Flight date |
| `DEP_HOUR` | Hour derived from departure time |
| `DAY_OF_WEEK` | Day of the week |
| `MONTH` | Month of the year |
| `DEP_DEL15` | Target variable |

**Target classes:**
- `0` — Departure delay below 15 minutes.
- `1` — Departure delay of 15 minutes or more.

##  Technologies Used

- Python
- Google Colab
- Hugging Face Datasets
- Pandas and NumPy
- scikit-fuzzy
- scikit-learn
- Matplotlib
- Genetic Algorithm

## Methodology

1. **Dataset Loading:** Load flight records from Hugging Face.
2. **Preprocessing:** Clean missing and invalid values and extract relevant features.
3. **Feature Scaling:** Normalize the inputs to a range of 0–10.
4. **Fuzzy Logic:** Use triangular membership functions and IF–THEN rules to generate a delay-risk score.
5. **Genetic Algorithm:** Optimize the membership-function boundary and classification threshold using F1-score as the fitness function.
6. **Evaluation:** Compare the baseline and GA-tuned models.
7. **Prediction:** Generate a delay classification for sample flight details.

## Model Details

### Fuzzy Logic

The system uses four inputs:
- Departure hour
- Flight distance
- Day of the week
- Month

Each input has three fuzzy sets: Low, Medium, and High. The output is a risk score between 0 and 100, which is converted into a binary prediction using a threshold.

### Genetic Algorithm

The GA searches for better parameter combinations through:

- Population initialization
- Fitness evaluation
- Selection
- Crossover
- Mutation
- Generation replacement

The best candidate is selected after the specified number of generations.

##  Evaluation Metrics

The models are evaluated using:

- **Accuracy:** Overall proportion of correct predictions.
- **Precision:** Correct positive predictions among all predicted positives.
- **Recall:** Actual positive cases correctly identified.
- **F1-score:** Balance between precision and recall.
- **Confusion Matrix:** Summary of correct and incorrect classifications.

The notebook generates a model comparison table and performance graph. Actual metric values should be added after running the notebook.

##  Sample Prediction

Example output from the notebook:

```text
Fuzzy risk score: 16.67 / 100
Prediction: Likely not delayed by 15+ minutes
```

The fuzzy risk score is a system-generated value, not a calibrated probability of delay.

## How to Run

1. Open [Google Colab](https://colab.research.google.com/).
2. Upload or open the project notebook (`.ipynb`).
3. Install the required libraries if they are not already available:

```python
!pip install -q datasets scikit-fuzzy scikit-learn pandas numpy matplotlib
```

4. Run the notebook cells in order.
5. Review the model metrics, confusion matrix, comparison table, and graph.

##  Limitations

- The fuzzy rules are manually defined.
- The selected features do not capture all causes of flight delays.
- The GA uses a small population and a limited number of generations.
- The implementation is a simplified educational model, not an exact reproduction of the referenced research paper.
- Performance on the sampled data may not generalize to all flights.

##  Future Enhancements

- Add weather, airline, and airport congestion data.
- Improve the fuzzy rule base.
- Compare against Logistic Regression, Decision Trees, and Random Forest.
- Use larger GA populations and more generations.
- Develop a web interface for flight delay predictions.
- Evaluate the model on unseen flight periods.

##  References

1. [Hugging Face Flight Delay Dataset](https://huggingface.co/datasets/Algo0o/flight_delay)
2. Kalić et al., *Data driven fuzzy logic system for flight delay prediction*(https://doi.org/10.1016/j.trpro.2026.07.017)
3. [scikit-fuzzy Documentation](https://scikit-fuzzy.readthedocs.io/)
4. [scikit-learn Documentation](https://scikit-learn.org/)

