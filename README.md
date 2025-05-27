# GB model for Predicting CIE
This repository contains the training pipeline and pre-trained model for predicting the CIE of ionic liquids based on QCP. 
The model is developed using a GB and evaluated using multiple performance metrics.

# Contents
- Bs_ionic.ipynb: Jupyter notebook with model training, hyperparameter tuning using GridSearchCV, data augmentation, and evaluation.
- Bs_ionic.pkl   : Pre-trained GB model saved in pickle format.

# Model Description
The model was trained using the following steps:
1. Data was scaled using RobustScaler.
2. Kernel Density Estimation (KDE) was used to augment the dataset.
3. A GradientBoostingRegressor was optimized using GridSearchCV over the following hyperparameter space:
   ```python
   param_grid = {
       'n_estimators': [100, 200, 300],
       'learning_rate': [0.01, 0.05, 0.1],
       'max_depth': [3, 5, 7],
       'min_samples_split': [2, 5, 10]
   }
