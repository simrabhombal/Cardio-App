## 📌 Machine Learning based Cardiovascular Disease Detection

This project presents two **independent machine learning pipelines** to predict cardiovascular disease (CVD) based on:

1. **ECG Image Classification** using Deep Learning (CNN)
2. **Biometric Parameter Classification** using Classical Machine Learning (Random Forest)

Both pipelines serve different diagnostic inputs but target the same objective — to provide an early and reliable assessment of cardiovascular health. These systems were trained, tested, and compared with multiple model architectures to select the most efficient and interpretable solution for each modality.

---

## 🎯 Project Aim

The aim of this project is to **automate the detection of cardiovascular disease** by leveraging Artificial Intelligence and Machine Learning. Cardiovascular diseases are a leading cause of global mortality, and early detection plays a crucial role in prevention and timely intervention.

We designed this system with the following goals:

- 🧠 **Intelligent Decision Support**: Assist medical professionals in analyzing ECG images and biometric data quickly and accurately.
- ⚙️ **Multi-modal Flexibility**: Enable users to either upload ECG images or enter biometric values, depending on the data available.
- 🌍 **Accessibility**: Improve access to disease detection in rural or resource-limited settings where expert cardiologists may not be available.

---

## 🧪 Comparative Study of Models

### 🔍 ECG Image Classification Models Tested:
| Model               | Accuracy | Remarks                                                                 |
|--------------------|----------|-------------------------------------------------------------------------|
| CNN                | **95.56%** | Selected for high accuracy and automatic feature extraction             |
| Random Forest      | 92%      | Required manual image preprocessing and feature flattening              |
| SVM                | 91%      | Performed poorly due to non-linear image features                       |
| Naive Bayes        | 89%      | Struggled with high-dimensional image data                              |

### ✅ Why CNN for ECG Images?
ECG signals are waveform patterns. Traditional ML models require hand-crafted feature extraction, which can miss crucial spatial patterns. CNNs learn these patterns automatically and efficiently.

---

### 📊 Biometric Classification Models Tested:
| Model               | Accuracy | Remarks                                                               |
|--------------------|----------|-----------------------------------------------------------------------|
| Random Forest       | **94%**  | Selected due to high performance, robustness, and interpretability   |
| XGBoost             | 92%      | High accuracy but computationally expensive                          |
| SVM                 | 90%      | Sensitive to hyperparameters and data scaling                        |
| K-Nearest Neighbors | 89%      | Performed poorly with large feature space                            |

### ✅ Why Random Forest for Biometrics?
Random Forest is ensemble-based and handles both numerical and categorical data very well. It is less prone to overfitting and provides **feature importance scores**, which are critical in healthcare to identify contributing factors in decision-making.

---

## ⚙️ How It Works

### 🧠 ECG Image Prediction (CNN-based)

- Input: ECG image uploaded by user
- Preprocessing: Resizing and normalization
- Model: CNN (3 Conv layers + Pooling + Dense layers)
- Output: Classification into `Normal`, `Abnormal`, or `Myocardial Infarction`

### 🩺 Biometric Parameter Prediction (RF-based)

- Input: User fills a form with age, gender, blood pressure, cholesterol, heart rate, etc.
- Preprocessing: Categorical encoding + standard scaling
- Model: Random Forest
- Output: Classification into `Normal` or `Abnormal`

Each system is standalone and doesn't depend on the other. Users can choose the path depending on the available data.

---

## 🧠 CNN Architecture for ECG Images (Explained in Detail)

CNNs are biologically inspired architectures that mimic how the visual cortex processes images. They are highly effective in identifying patterns in image data, which makes them ideal for analyzing ECG waveforms.

### 🏗 Architecture:
- **Input Layer**: ECG image (resized to 224x224)
- **Conv2D Layer 1**: 32 filters, 3x3 kernel, ReLU → MaxPooling2D
- **Conv2D Layer 2**: 64 filters, 3x3 kernel, ReLU → MaxPooling2D
- **Conv2D Layer 3**: 128 filters, 3x3 kernel, ReLU → MaxPooling2D
- **Flatten Layer**
- **Dense Layer**: 256 units with ReLU
- **Dropout**: 40% to prevent overfitting
- **Output Layer**: 3 neurons with Softmax activation

### 📈 Theoretical Advantages:
- CNNs capture **local dependencies** via filters.
- **Translation invariance** using pooling layers.
- Excellent for identifying subtle differences between ECG conditions (e.g., ST elevation).

### ✅ Results:
- **Final Accuracy**: **95.56%**
- **Loss Function**: Categorical Cross-Entropy
- **Optimizer**: Adam
- **Epochs**: Tuned using early stopping

---

## 🌲 Random Forest for Biometric Parameters (Explained in Depth)

Random Forest is an ensemble learning method that builds multiple decision trees and merges them to get a more accurate and stable prediction.

### 🧬 Features Used:
- Age
- Sex
- Resting Blood Pressure
- Serum Cholesterol
- Fasting Blood Sugar
- Max Heart Rate
- Exercise-Induced Angina
- ST Depression, etc.

### 🏗 Architecture (Implemented from Scratch):
- **Number of Trees**: 100 (tuned via cross-validation)
- **Depth of Tree**: Tuned (best found around 10–20)
- Each tree trained on a **bootstrap sample**
- Each split selects random subset of features
- Final prediction = **majority vote** across trees

### 📈 Theoretical Advantages:
- Handles both **numerical and categorical** variables
- Reduces overfitting via ensemble averaging
- **Interpretable** through feature importance
- **Robust to noise** and data imbalance

### ✅ Results:
- **Final Accuracy**: 94%
- Compared models: XGBoost (92%), SVM (90%), KNN (89%)
- Random Forest selected for **generalization, speed, and medical interpretability**

---
## 🔧 How to Run the Project (Flask App)

To run this Flask-based cardiovascular disease detection project, follow these steps:

### 1. Clone the Repository  
Open your terminal or command prompt and run the following commands to clone the repository and move into the project directory:  

```bash
git clone (https://github.com/simrabhombal/Cardio-App.git)
```
### 2. Install the Required Dependencies
Make sure Python (preferably 3.7 or higher) and pip are installed on your system. Then install the required Python packages

### 3. Run the Flask Application
Once dependencies are installed, start the Flask development server by running:
```bash
python manage.py
```
You should see the output like this : 
Running on http://127.0.0.1:5000/

### Project Video:
https://www.youtube.com/watch?v=hAqDUL6PYCc


