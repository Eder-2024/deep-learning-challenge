# 📊 Overview of the Analysis

- The goal of this project was to build a deep learning model that could predict whether a nonprofit organization's funding application would be successful.
- The dataset included various features such as the type of application, use case, income level, and more.
- The target was to reach a model accuracy of at least **75%**.

---

# 🔧 Data Preprocessing

- **Target Variable:**
  - `IS_SUCCESSFUL`: Binary target (1 = successful, 0 = not).

- **Feature Variables:**
  - All columns except the target, including:
    - `APPLICATION_TYPE`, `AFFILIATION`, `CLASSIFICATION`, `USE_CASE`, `INCOME_AMT`, `ASK_AMT`, etc.

- **Removed Columns:**
  - `EIN` and `NAME` — dropped as they are just identifiers with no predictive value.

- **Additional Preprocessing Steps:**
  - Grouped rare values in `APPLICATION_TYPE` and `CLASSIFICATION` into an `"Other"` category.
  - Applied one-hot encoding to categorical features.
  - Scaled features using `StandardScaler` to normalize the input data.

---

# ⚙️ Compiling, Training, and Evaluating the Model

I trained three different neural network models, each with variations to try and improve performance.

## ✅ Model 1: Basic Network
- **Structure**: 2 hidden layers (80 and 30 neurons)
- **Activations**: ReLU for hidden layers, Sigmoid for output
- **Result**: Accuracy = **72.6%**

## ✅ Model 2: Regularized Network
- **Changes**:
  - Added Dropout layers
  - Reduced learning rate
- **Structure**: 3 hidden layers (100, 50, 20 neurons)
- **Dropout**: 20% after the first two layers
- **Result**: Accuracy = **72.8%**

## ✅ Model 3: Batch Normalization + EarlyStopping
- **Changes**:
  - Added Batch Normalization layers
  - Introduced EarlyStopping to prevent overfitting
  - Slight learning rate adjustment
- **Structure**: 3 hidden layers (64, 32, 16 neurons)
- **Result**: Accuracy = **73.0%**
- **Note**: Training stopped early (at epoch 20) due to no further improvement in validation loss.

---

# 📈 Model Evaluation

- **Final Model Performance on Test Set:**
  - **Loss**: 0.5563  
  - **Accuracy**: 73.02%

- While the target accuracy of 75% wasn’t reached, the model performed consistently and generalizes reasonably well.

---

# 🧾 Summary

## ✅ Summary:
- Successfully built and trained three neural network models on the dataset.
- Final model achieved **73.02%** accuracy — close to the target and an improvement over the initial baseline.


