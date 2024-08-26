# Mergers & Acquisitions: Predicting IBM Acquisition Costs Using Decision Trees & Random Forests Regressors
Charlize Samuels

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
- The **Decision Tree Regressor** showed the following performance:
    - **Cross-Validation MSE**: `6.13e+19`
    - **Test MSE**: `4.15e+19`
    - Despite pre-pruning techniques, the Decision Tree model displayed high variance and struggled to generalize well. The relatively large difference between cross-validation MSE and test MSE suggests that the model might still be overfitting, especially considering the small dataset.

- The **Random Forest Regressor** outperformed the Decision Tree, with the following results:
    - **Cross-Validation MSE**: `4.24e+19`
    - **Test MSE**: `2.09e+19`
    - The Random Forest model demonstrated better generalization compared to the single Decision Tree, as evidenced by the lower MSE scores. The ensemble method's ability to aggregate multiple trees reduced overfitting and improved the model’s predictive power on unseen data.

### Implications
- The significant difference in MSE between the two models highlights the advantage of using ensemble methods, especially with small datasets that are prone to overfitting. The Random Forest’s lower MSE indicates that it is more reliable for predicting acquisition costs, providing more stable and accurate estimates.
- Although the MSE values are large, the comparison between models shows that the Random Forest model is better suited for this task, capturing the patterns in the data more effectively.

## Repository Structure
- `acquisitions_update_2021.csv`: Contains the dataset used for the project.
- `M&A_Tech_ML`: Jupyter notebook with the data exploration, model development, and evaluation steps.
- `README.md`: This documentation file.
