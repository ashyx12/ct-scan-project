# Machine Learning Framework for Multi-Class Cerebrovascular CT Lesion Classification

### **1. Dataset**
* **Source**: Kaggle cerebrovascular lesion dataset (Macin et al., 2025).
* **Content**: 10 classes (acute ischemic infarction, epidural hemorrhage, chronic ischemic infarction, etc.), ~10K CT images.
* **Preprocessing**:
    * Grayscale conversion
    * Resize to uniform dimensions (`128×128`)
    * Normalization (pixel intensity scaling)
* **Split**: Train/test (stratified train-test split).

***

### **2. Radiomics Feature Extraction**

#### **2.1 Edge & Shape Features**
* **Histogram of Oriented Gradients (HOG)** → captures edges & gradients.

#### **2.2 Local Texture Features**
* **Local Binary Patterns (LBP)** → micro-texture representation.

#### **2.3 Co-occurrence Features**
* **Gray-Level Co-occurrence Matrix (GLCM)** → co-occurrence statistics (contrast, correlation, homogeneity, energy).

#### **2.4 Statistical Features**
* **Haralick Descriptors** (derived from GLCM) → 14 classic texture descriptors (entropy, difference variance, etc.).

#### **2.5 Frequency/Filter-Based Features**
* **Gabor Filters** → multi-scale, multi-orientation texture filters.

> **Combined** → Comprehensive Radiomics Feature Set.

***

### **3. Machine Learning Models**
Benchmark 9 algorithms:
1.  Logistic Regression
2.  K-Nearest Neighbors (KNN)
3.  Support Vector Machine (SVM)
4.  Naive Bayes
5.  Decision Tree
6.  Random Forest
7.  XGBoost
8.  AdaBoost
9.  Multi-Layer Perceptron (MLP)

> Each model is trained on the same feature set, so results are comparable.

***

### **4. Evaluation Metrics**
* **Accuracy**
* **Macro-F1 Score** (handles class imbalance)
* **Balanced Accuracy** (accounts for skewed classes)
* **Standard Deviation** across folds (stability)

***
