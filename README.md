# Heart-Disease

## Description

Heart-Disease is a project aimed at predicting the presence of heart disease based on various medical attributes. The project utilizes machine learning algorithms to analyze the dataset and provide accurate predictions.

## Table of Contents

- [Usage](#usage)
  - [Option 1: Use Google Colab with GitHub integration](#option-1-use-google-colab-with-github-integration)
  - [Option 2: Clone The Repository and Upload The Notebook Manually](#option-2-clone-the-repository-and-upload-the-notebook-manually)
- [Dataset](#dataset)
- [Models](#models)
- [Data Understanding and Visualization](#data-understanding-and-visualization)
- [Dealing with Missing Values](#dealing-with-missing-values)
- [Label Encoding](#label-encoding)
- [One-Hot Encoding](#one-hot-encoding)
- [Outlier Detection](#outlier-detection)
- [Feature Selection & Model Training](#feature-selection--model-training)
- [Contributing](#contributing)
- [License](#license)

## Usage

To use this project, follow these steps:

### Option 1: Use Google Colab with GitHub integration

1. Go to [Google Colab](https://colab.research.google.com/) website.
2. Click on the `File` tab in the top-left corner of the Colab homepage.
3. Select "Open notebook" from the dropdown menu.
4. In the `GitHub` tab, paste the link to the notebook: [heart_disease.ipynb](https://github.com/MHRasmy/Heart-Disease/blob/main/heart_disease.ipynb).
5. Press the `Enter` key or click the search icon.
6. The notebook will open in a new tab.
8. Click on the `Runtime` tab in the menu at the top.
9. Select `Run all` to execute all the code cells in the notebook.

### Option 2: Clone The Repository and Upload The Notebook Manually

1. Clone the repository using the following command in your local terminal:
```shell
git clone https://github.com/MHRasmy/Heart-Disease.git
```
2. Navigate to the cloned directory:
```shell
cd Heart-Disease
```
3. Locate the notebook file `heart_disease.ipynb` in the cloned repository.
4. Open Google Colab in your web browser.
5. Click on the `File` tab and select `Upload notebook`.
6. Choose the `heart_disease.ipynb` file from your local directory.
7. Once the file is uploaded, the notebook will open in Colab.
8. Click on the `Runtime` tab in the menu at the top.
9. Select `Run all` to execute all the code cells in the notebook.

- Make sure you have uploaded the dataset [Heart_Disease.csv](https://github.com/MHRasmy/Heart-Disease/blob/main/Dataset/Heart_Disease.csv) to your Colab environment. You can do this by clicking on the `Files` tab on the left-hand side, then clicking on the `Upload` button. The dataset should be available in the same directory or folder where the notebook is executed.
- Feel free to modify the code or experiment with different parameters to further analyze and predict heart disease.

## Dataset

The dataset used for training and testing the model is stored in the [dataset](https://github.com/MHRasmy/Heart-Disease/tree/main/Dataset) directory. It contains several medical attributes such as age, sex, cholesterol levels, etc., along with the target variable indicating the presence or absence of heart disease.

## Data Understanding and Visualization

To start the project, the columns in the dataset were analyzed and identified key features such as age, gender, blood pressure, cholesterol level, and chest pain type. Potential predictors of heart disease were also explored, such as work type and smoking status. Visualization techniques like histograms were used to identify outliers and gain insights into potential predictors of heart disease.

## Dealing with Missing Values

The project handles missing values in the dataset by using interpolation for the 'Age' column and filling the 'work type', 'gender', and 'smoking status' columns with the mode of the entire data. The 'id' column, lacking relevant information, is dropped. The relationship between gender and smoking status is analyzed using a contingency table and chi-square test of independence.

To handle missing values in the 'smoking status' column, 'Unknown' values are replaced with the mode of the entire column. Feature selection is performed using the chi-square test of independence to identify significant variables related to the target variable. One-hot encoding is applied to the 'work type' and 'smoking status' features using the 'get_dummies' function of Pandas. The encoded data is then concatenated with the original data, and the original features are dropped to prevent multicollinearity.

## Label Encoding

Label encoding is used to convert categorical data into numerical data that can be used in machine learning models for prediction. It assigns a unique integer value to each category, transforming it into a numerical representation. In this project, label encoding is applied to the 'Gender' and 'Heart Disease' columns.

## One-Hot Encoding

One-hot encoding is a technique used to convert categorical data into a binary format that can be used in machine learning models. It creates binary columns for each unique category in the categorical feature and assigns a value of 1 or 0 to indicate the presence or absence of a category in a particular sample. One-hot encoding is particularly useful when dealing with categorical features that do not have a natural order or hierarchy. In this project, one-hot encoding is applied to the 'work type' and 'smoking status' columns.

## Outlier Detection

The project also deals with potential outliers in the dataset. It calculates the mean and standard deviation of each column and identifies columns with significant differences in range, mean, or standard deviation. The names of these columns, which may contain outliers, are printed. Outliers are detected using the interquartile range (IQR) method. Values falling below (Q1 - 1.5 * IQR) or above (Q3 + 1.5 * IQR) are considered outliers and replaced with the maximum and minimum values in the range for each column.

## Feature Selection & Model Training

Feature selection is performed to select the best features for the input data. The input data is normalized using the MinMaxScaler, and the SelectKBest class is used with the chi-squared test as the scoring function. The top features are selected based on the specified number, and the data is split into training and testing sets. Logistic Regression, Support Vector Machine (SVM), and Decision Tree models are trained and evaluated using accuracy score, confusion matrix, classification report, and mean squared error.

A Random Forest Classifier model is also trained with 200 estimators, and its performance is evaluated using accuracy score, confusion matrix, and classification report. Another Random Forest Classifier model is trained until the accuracy on the test set reaches 0.94444, and its performance is evaluated using a confusion matrix, classification report, and accuracy score.


## Contributing

Contributions to this project are welcome. If you find any bugs or have suggestions for improvements, please open an issue or submit a pull request. Make sure to follow the project's coding style and guidelines.

## License

This project is licensed under the [MIT License](LICENSE).
