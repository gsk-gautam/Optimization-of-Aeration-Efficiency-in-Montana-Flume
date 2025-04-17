# 🌊 Study on Aeration Efficiency in Montana Flume

## 📘 Overview

This project investigates **aeration efficiency** in Montana flumes using both experimental and machine learning approaches. Aeration—critical for water treatment and aquatic systems—is evaluated through physical modeling, non-dimensional analysis, and multiple machine learning models.

The objective is to analyze how geometric parameters, flow conditions, and setup positions influence aeration, and to develop predictive models for estimating aeration efficiency.

## 🧪 Experimental Setup

The experiment involves:
- **Modified Montana flumes** (6 total – 2 standard, 4 custom)
- **DO meter** for oxygen measurement
- A **re-circulating water channel** with variable discharge control
- DO alteration using **sodium sulfite and cobalt chloride**

### Key Parameters:
- **DO at Upstream and Downstream**
- **Flow Depth**
- **Water Temperature**
- **Position of Flume** in channel

## 🧠 Machine Learning Models Used

Various regression models were developed to predict **aeration efficiency (E20)** from experimental data:

| Model                      | Description |
|---------------------------|-------------|
| Multi-Linear Regression   | Simple linear mapping of input features |
| Random Forest Regressor   | Ensemble tree-based model capturing non-linearities |
| K-Nearest Neighbors       | Prediction based on similar data points |
| Feedforward Neural Network | Deep learning model for pattern recognition |
| Multi Non-Linear Regression | Polynomial/kernel based regression |
| Layer Recurrent Neural Network (LRNN) | Captures time-related dependencies |
| Recurrent Neural Network (RNN) | Sequence-based neural model (LSTM/GRU) |

### ✅ Best Performing Model:
**Layer Recurrent Neural Network (LRNN)** – Achieved the highest **R² score** and lowest **RMSE**.

## 📈 Data Insights

- **Reynolds number** was found to be the most sensitive and strongly correlated with aeration efficiency.
- **Froude number** had the least influence.
- **Aeration is more effective** when the flume is placed at the **end** of the channel compared to the center.
- Flumes with a **larger throat length** showed improved efficiency due to increased air-water contact time.

## 📊 Key Equations

**Aeration Efficiency (E):**
```
E = (Cd - Cu) / (Cs - Cu)
```

**Corrected to 20°C (E20):**
```
(1 - E20) = (1 - E)^(1/f)
```

**Gulliver Temperature Correction Factor:**
```
f = 1 + 0.02103(T - 20) + 8.261 × 10⁻⁵(T - 20)²
```

## 📁 Project Structure

```
📦 Montana-Flume-Aeration
├── 📄 README.md
├── 📊 data/
│   ├── raw_measurements.csv
│   ├── preprocessed_data.csv
├── 🧠 models/
│   ├── linear_regression.py
│   ├── random_forest.py
│   ├── neural_networks.py
├── 📈 results/
│   ├── evaluation_metrics.csv
│   ├── correlation_graphs.png
├── 📄 submission_report.pdf
```

## 🛠 Tools & Libraries

- Python (NumPy, Pandas, Matplotlib, Scikit-learn, TensorFlow/Keras)
- Jupyter Notebook
- DO Meter & Physical Lab Instruments
- Google Sheets for Data Logging

## 📌 Team Members

- Gautam Kumar  
- Bokka Sudha Sri  
- Garima Mandli  
- Goli Gayathri  
- Pravas Mishra  

**Supervisor**: Prof. K.S. Hari Prasad

## 🔗 References

- [Two-Film Theory – Lewis & Whitman, 1924]
- [Experimental DO Data (Google Sheet)](https://docs.google.com/spreadsheets/d/1GinMN98Dne89PTL9nmAgxf_nA6zgQjEW)
- [Montana Flume Literature & Blueprints](https://drive.google.com/drive/folders/1FUDu3M8BfC0exelf_bpNjkW8mNxvLkPE?usp=sharing)

## 🚀 Future Scope

- Deploy real-time DO sensors in field conditions
- Apply model to different flume geometries and flow regimes
- Extend ML models to other aeration structures like cascades or weirs
