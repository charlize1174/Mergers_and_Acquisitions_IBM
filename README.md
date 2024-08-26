 IBM M&A Acquisition Cost Prediction Using Decision Trees & Random Forests Regressors

## Project Overview
This project aims to predict the acquisition cost of IBM's M&A deals based on key factors such as country, business type, and year. By leveraging machine learning models like Decision Trees and Random Forests, the goal is to explore whether we can accurately estimate acquisition costs and understand which features have the most influence on these predictions.

### Research Question
**Can we predict acquisition cost for IBM M&A deals based on country, business type, and year?**

## Introduction and Relevance
Mergers and Acquisitions (M&A) play a critical role in a company’s growth strategy. Understanding the drivers of acquisition costs is essential for making informed decisions and setting realistic expectations in future deals. IBM is a significant player in the tech industry, known for its strategic acquisitions. By focusing exclusively on IBM’s acquisition data, this project seeks to uncover patterns and build predictive models that could provide insights into what drives acquisition costs.

## Methodology and Model Choice
### 1. **Data Collection and Preprocessing**
- The dataset contains IBM’s acquisition data with variables such as `Country`, `Business Type`, `Acquisition Year`, and `Acquisition Price`.
- Data preprocessing steps included categorical encoding (for `Country` and `Business Type`) and inflation adjustment to account for the real value of acquisition prices over time.

### 2. **Model Choices**
- **Decision Tree Regressor**: Chosen for its interpretability and ability to capture non-linear relationships. Pre-pruning techniques were applied to avoid overfitting:
    - **Max Depth**: Limited the depth of the tree to prevent it from becoming overly complex.
    - **Min Samples Split**: Controlled the minimum number of samples needed to split a node, reducing the likelihood of splits based on noise.
    - **Min Samples Leaf**: Set a minimum number of samples required at each leaf node to prevent overly specific splits.
- **Random Forest Regressor (Ensemble Method)**: Selected to improve robustness and accuracy by averaging the results of multiple decision trees, reducing the variance and providing more stable predictions.

### 3. **Model Evaluation**
- Models were evaluated using Mean Squared Error (MSE) on both the training and test datasets, with k-fold cross-validation used to validate performance.

## Final Results and Conclusions
- The **Decision Tree Regressor** provided a baseline performance with an MSE of `X` on the test set. While it offered interpretability, the model was prone to slight overfitting, especially given the small dataset size.
- The **Random Forest Regressor** outperformed the decision tree, achieving a lower MSE of `Y`, indicating better generalization and more accurate predictions. Feature importance analysis revealed that business type and acquisition year were the most influential factors in predicting acquisition costs.

### Conclusion
This project demonstrates that ensemble methods like Random Forests can significantly improve prediction accuracy over single decision trees, particularly in scenarios with small datasets. The analysis also highlighted key drivers of acquisition costs for IBM, providing valuable insights for future strategic decisions.

## Repository Structure
- `acquisitions_update_2021.csv/`: Contains the dataset used for the project.
- `M&A_Tech_ML/`: Jupyter notebook with the data exploration, model development, and evaluation steps.
- `README.md`: This documentation file.
