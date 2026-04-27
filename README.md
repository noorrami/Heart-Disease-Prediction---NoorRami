# 💓 Heart Disease Prediction 

## 📝 Objective
Build a binary classification model to predict whether a patient has heart disease based on clinical features. This task emphasizes data cleaning, exploratory data analysis, model evaluation (including ROC curve and confusion matrix), and feature importance extraction.

## 📁 Dataset
- **Source**: [UCI Heart Disease Dataset](https://www.kaggle.com/datasets/redwankarimsony/heart-disease-data)
- **Samples**: 920
- **Original features**: 16 (including `id`, `dataset`, `num` as multi-class target)
- **Processed features**: 14 (removed non-medical columns, binary target)

## 🛠️ Tools & Libraries
- `pandas`, `numpy` – data manipulation
- `matplotlib`, `seaborn` – visualization
- `scikit-learn` – preprocessing, modeling, evaluation

## 📊 Workflow (Steps)

1. **Data Loading & Initial Inspection**  
   - Load CSV directly from URL.
   - Check shape, data types, missing values.

2. **Handling Missing Values**  
   - Numerical columns → `SimpleImputer(strategy='median')`
   - Categorical columns → `SimpleImputer(strategy='most_frequent')`

3. **Encoding Categorical Features**  
   - Use `LabelEncoder` for all object columns.

4. **Binarize Target**  
   - Original target `num` (0–4) → `target_binary` (0 = no disease, 1 = disease).

5. **Drop Non-Medical Features**  
   - Removed `id` and `dataset` to prevent data leakage and improve generalization.

6. **Exploratory Data Analysis**  
   - Target distribution, correlation heatmap, histograms, boxplots, count plots by chest pain type, etc.

7. **Train/Test Split**  
   - 80% train, 20% test, `stratify=y` to preserve class balance.

8. **Feature Scaling**  
   - `StandardScaler` applied only to features for Logistic Regression (not needed for Decision Tree).

9. **Model Training**  
   - Logistic Regression (baseline, interpretable)  
   - Decision Tree (max_depth=5 to reduce overfitting)

10. **Evaluation**  
    - Accuracy, classification report, confusion matrix, ROC curve & AUC.
    - Compared train/test accuracy to detect overfitting.

11. **Feature Importance**  
    - Extracted from Decision Tree and visualized with a bar plot.

12. **Conclusion & Recommendation**  
    - Logistic Regression chosen as final model (82.07% test accuracy, no overfitting).

## 📈 Results

| Model | Train Accuracy | Test Accuracy | Overfitting | AUC (approx) |
|-------|---------------|---------------|-------------|---------------|
| Logistic Regression | 81.11% | **82.07%** | ❌ No | 0.89–0.91 |
| Decision Tree | 83.15% | 77.17% | ⚠️ Mild | – |

### 🩺 Top 3 Important Features (from Decision Tree)
1. **`cp` (Chest Pain Type)** – 45.8%  
2. **`chol` (Cholesterol)** – 17.6%  
3. **`age` (Age)** – 9.7%

*These align with clinical knowledge, validating the model's reliability.*

## 🚀 How to Run
1. Clone the repository.
2. Install required packages: `pip install pandas numpy matplotlib seaborn scikit-learn`
3. Open `Task3_Heart_Disease_Prediction.ipynb` in Jupyter Notebook or VS Code.
4. Run all cells sequentially.

## 📌 Conclusion
Logistic Regression achieved **82.07% test accuracy** with no overfitting, making it suitable for educational purposes. The most influential features (`cp`, `chol`, `age`) are clinically meaningful. Removing `id` and `dataset` was crucial to avoid data leakage and improve model generalizability.

## 📂 Repository Structure


## 👤 Author
[Noor Rami Saad] – AI/ML Engineering Intern @ DevelopersHub Corporation

## 📅 Due Date
27th April, 2026
