House Price Prediction Using Linear Regression
Faculty Submission
Detail	Information
Project / Activity Title	House Price Prediction Using Linear Regression
Subject	Machine Learning
Faculty ID	https://github.com/complexiota
Submitted By	Karan Sandip Kadam
Class / Division	AIDS (B)
Roll Number	AD3204
Academic Year	2026–27
Submitted To	______________________________
Submission Date	______________________________


1. Introduction
This activity builds and evaluates machine learning regression models to predict house prices using
selected numerical features from the housing dataset. It compares a single-feature Linear Regression model with a multiple-feature Linear Regression model.
3. Objectives
- Load and inspect the housing dataset.
- Check data types, missing values, and duplicate records.
- Explore relationships between house features and price.
- demonstrate the manual least-squares calculation for Linear Regression.
- Train single-feature and multiple-feature regression models.
- Evaluate model performance using regression metrics.
- Inspect residuals and calculate Variance Inflation Factor (VIF).
- Predict the price of a sample house.
3. Dataset
File required: Housing.csv

The notebook reads the dataset using pd.read_csv("Housing.csv").
- Initial dataset size: 545 rows × 13 columns
- Target variable: price
- Features used by the models:
  - area
  - bedrooms
  - bathrooms
  - stories
  - parking
The dataset inspection reported no missing values and no duplicate rows. The notebook also applies duplicate removal
 and drops rows missing any selected feature or the target.
Keep Housing.csv in the same directory as the notebook before running it.

4. Tools and Libraries
- Python
- Jupyter Notebook
- Pandas
- NumPy
- Matplotlib
- Scikit-learn
5. Methodology
1. Import libraries: Load the data analysis, plotting, and machine learning libraries.
2. Load and inspect data: Read Housing.csv and review its shape, information, descriptive statistics, missing values, and duplicate rows.
3. Clean data: Remove duplicate rows and rows with missing values in the selected features or target.
4. Exploratory data analysis: Plot each selected feature against house price and create a correlation heatmap.
5. Manual Linear Regression: Use a six-row sample with area and bedrooms to calculate the least-squares coefficients using the normal equation:
   b = (XᵀX)⁻¹ Xᵀy
6. Train models: Split the data into training and testing sets using an 80:20 split and random_state=42. Train:
   - Single-feature model using area.
   - Multiple-feature model using all five selected features.
7. Standardisation: Fit a StandardScaler on the training features and inspect the standardised model coefficients.
8. Prediction and evaluation: Predict test-set prices and calculate MAE, MSE, RMSE, R², and Adjusted R².
9. Diagnostics: Plot residuals, a residual histogram, and actual-versus-predicted prices. Calculate VIF values for the selected features.
10. Sample prediction: Predict the price for a house whose feature values are set to the training-set medians.
6. Model Results
The notebook produced the following test-set results:
Metric	Single-feature model (area)	Multiple-feature model
MAE	1,474,748	1,127,483
MSE	3.675287 × 10¹²	2.292722 × 10¹²
RMSE	1,917,104	1,514,174
R²	0.272879	0.546406
Adjusted R²	0.266083	0.524387


Interpretation: The multiple-feature model performs better on this test split. It has lower MAE, MSE, and RMSE, and higher R² and Adjusted R² than the single-feature model.
Multiple Regression Equation
The fitted multiple-feature model is:
Price = 51999.68
      + (308.87 × area)
      + (151246.75 × bedrooms)
      + (1185731.71 × bathrooms)
      + (495100.76 × stories)
      + (337660.83 × parking)
VIF Results
Feature	VIF
area	1.157790
bedrooms	1.332267
bathrooms	1.269826
stories	1.241431
parking	1.154152


The calculated VIF values are close to 1, indicating low multicollinearity among the selected predictors in this training set.
7. Sample House Prediction
The notebook uses the following training-set median values:
Feature	Value
area	4500
bedrooms	3
bathrooms	1
stories	2
parking	0


Predicted price: 4,071,574.47 (in the price units used by the dataset).
8. How to Run the Notebook
1. Install Python and Jupyter Notebook (or use JupyterLab / Google Colab).
2. Place ActivityRCA1.ipynb and Housing.csv in the same folder.
3. Install the required packages:
   pip install pandas numpy matplotlib scikit-learn jupyter
4. Start Jupyter:
   jupyter notebook
5. Open ActivityRCA1.ipynb.
6. Run all cells from top to bottom.
9. Conclusion
This activity demonstrates the complete workflow of a basic house-price regression task, from data inspection and exploratory analysis to model training, evaluation, diagnostics, and prediction. Based on the reported test results, the multiple-feature Linear Regression model gives better predictive performance than the single-feature model using area alone.
