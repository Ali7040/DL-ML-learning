# Phase 2: Classical Machine Learning 🤖

**Duration:** Weeks 9-20 (3 months)  
**Goal:** Master traditional ML algorithms from theory to implementation

## Overview

Classical ML algorithms are still widely used in industry and form the foundation for understanding deep learning. You'll implement each algorithm from scratch before using libraries.

## Folders

### Supervised-Learning/
- **Regression/**: Linear, Polynomial, Ridge, Lasso, Elastic Net
- **Classification/**: Logistic Regression, SVM, Decision Trees, Ensembles

### Unsupervised-Learning/
- **Clustering/**: K-Means, Hierarchical, DBSCAN, GMM
- **Dimensionality-Reduction/**: PCA, LDA, t-SNE, UMAP

### Projects/
End-to-end ML projects

## Weekly Breakdown

### Week 9-10: Regression
- [ ] Linear Regression (theory + implementation)
- [ ] Polynomial features
- [ ] Regularization (L1, L2)
- **Project:** Housing price prediction

### Week 11-13: Classification
- [ ] Logistic Regression
- [ ] SVM (linear and kernel)
- [ ] Decision Trees
- [ ] Naive Bayes, KNN
- **Project:** Customer churn prediction

### Week 14-15: Ensemble Methods
- [ ] Random Forests
- [ ] Gradient Boosting
- [ ] XGBoost, LightGBM
- **Project:** Kaggle competition entry

### Week 16-17: Unsupervised Learning
- [ ] K-Means implementation
- [ ] Hierarchical clustering
- [ ] PCA from scratch
- **Project:** Customer segmentation

### Week 18-20: Advanced Concepts & Projects
- [ ] Feature engineering techniques
- [ ] Hyperparameter tuning
- [ ] Model interpretation (SHAP, LIME)
- **Projects:** 3 end-to-end ML projects

## Algorithms to Implement from Scratch

### Must Implement (No Libraries)
1. Linear Regression with gradient descent
2. Logistic Regression
3. Decision Tree (ID3 or CART)
4. K-Means clustering
5. PCA
6. K-Nearest Neighbors
7. Naive Bayes

### Implement with NumPy Only
8. Random Forest
9. Linear SVM
10. Hierarchical clustering

### Use Libraries (After Understanding)
11. SVM with kernels (sklearn)
12. XGBoost, LightGBM
13. Advanced ensemble methods

## Key Concepts to Master

### Supervised Learning
- Bias-variance tradeoff
- Overfitting vs underfitting
- Cross-validation strategies
- Regularization techniques
- Evaluation metrics (precision, recall, F1, AUC-ROC)

### Unsupervised Learning
- Distance metrics
- Silhouette score
- Elbow method
- Explained variance
- Intrinsic dimension

### General
- Train-test-validation split
- Feature scaling and normalization
- Handling imbalanced data
- Feature selection methods
- Pipeline creation

## Practice Projects

### Beginner Projects
1. **House Price Prediction**
   - Regression problem
   - Feature engineering
   - Model comparison

2. **Iris Classification**
   - Multiclass classification
   - Visualization
   - Different classifiers

3. **Customer Segmentation**
   - K-Means clustering
   - PCA visualization
   - Business insights

### Intermediate Projects
4. **Credit Card Fraud Detection**
   - Imbalanced data handling
   - Precision-recall focus
   - Multiple models

5. **Customer Churn Prediction**
   - Binary classification
   - Feature importance
   - Business recommendations

6. **Movie Recommendation System**
   - Collaborative filtering
   - Matrix factorization
   - Evaluation metrics

### Advanced Projects
7. **End-to-end Pipeline**
   - Data ingestion
   - Preprocessing
   - Model training
   - Evaluation
   - Deployment ready

8. **Kaggle Competition**
   - Real competition
   - Feature engineering
   - Model ensembling
   - Leaderboard submission

## Learning Resources

### Books
- "Pattern Recognition and Machine Learning" by Bishop
- "The Elements of Statistical Learning" by Hastie et al.
- "Hands-On Machine Learning" by Aurélien Géron

### Courses
- Andrew Ng's Machine Learning Course
- Stanford CS229

### Papers
- Original papers for each algorithm
- Survey papers on ensemble methods

## Assessment Checklist

Can you:
- [ ] Derive the gradient for linear/logistic regression?
- [ ] Implement gradient descent from scratch?
- [ ] Explain bias-variance tradeoff with examples?
- [ ] Build a decision tree by hand?
- [ ] Calculate information gain/Gini index?
- [ ] Understand kernel trick in SVM?
- [ ] Implement PCA from scratch?
- [ ] Choose appropriate evaluation metrics?
- [ ] Handle imbalanced datasets?
- [ ] Perform end-to-end ML project independently?
- [ ] Explain predictions using SHAP/LIME?
- [ ] Optimize hyperparameters systematically?

## Common Mistakes to Avoid

1. Using libraries without understanding
2. Not validating properly (data leakage)
3. Ignoring feature scaling
4. Wrong metric for the problem
5. Not handling imbalanced data
6. Overfitting on small datasets
7. Not documenting experiments
8. Comparing models unfairly

## Daily Practice Template

```python
# Day X: [Algorithm Name]
# 1. Theory: Read and understand math
# 2. Implement from scratch (NumPy only)
# 3. Test on simple dataset
# 4. Compare with sklearn implementation
# 5. Apply to real dataset
# 6. Document learnings
```

## Kaggle Competitions to Try

- Titanic (classification)
- House Prices (regression)
- Digit Recognizer (classification)
- Santander Customer Satisfaction

## Next Phase

After mastering classical ML, move to [03-Deep-Learning-Fundamentals](../03-Deep-Learning-Fundamentals/README.md)

---

**Key Insight:** Most real-world problems can be solved with classical ML. Master this before deep learning! 🎯
