# Phishing Detection Using Machine Learning

The phishing detection model leverages machine learning to effectively classify emails as phishing or legitimate based on their content. This model provides significant value in enhancing email security by automating the identification of potentially harmful phishing emails, thereby reducing the risk of security breaches and protecting sensitive information.

<div align="center">
  <img src="images/powerupmlphishing.png" alt="Cover Image">
</div>


## Prequisities and Installation Steps

Below are the steps outlined for installation. Please make sure to have python, the necessary libaries, and Jupyter Notebook installed in order to successfully execute the steps within your notebook. 

Additionally, you will need a dataset for testing. This example uses the "spam_or_not_spam.csv" file from [Kaggle](https://www.kaggle.com/). Be mindful of the filepath where the  dataset will be stored. The .csv file should be located where you cloned your respository. Prior to running the cell operation, the location of this file path will need to be updated in your notebook when reaching step 4 in the installation process.

1.1 **Optional: Create a python virtual environment to isolate this library
```bash
python3 -m venv phishing_env
source activate phishing_env/bin/activate
```

1.2 **Clone the repository and navigate to the project directory. The files here will be used and referenced with your installation setup process.**
```bash
git clone https://github.com/powerupcyber/phishing-detection.git
cd phishing-detection
```

1.3 **Install Python 3.x:**
   - Download and install Python from the [official website](https://www.python.org/downloads/).
   - Follow the installation instructions for your operating system.

1.4 **Install Jupyter Notebook:**
   - Install Jupyter Notebook using the following command:
     ```
     !pip3 install notebook
     ```
   - After installation, start Jupyter Notebook by running:
     ```
     jupyter notebook
     ```

1.5. **Install Required Libraries:**
   - Install the required Python libraries using the following command in your Jupyter Notebook. This will  be the first cell operation that you will need to run. Optional: For mac users, Press "command + space" button or open Spotlight - type "Install Certificates.command" if you run into any ssl issues on Python, particularly when downloading the nltk library.
     ```
     !pip3 install pandas nltk scikit-learn joblib
     ```
	 
1.6. **Open Jupyter Notebook:**
   - With your Jupyter Notebook running, make sure the `ML_Phishing_Detection.ipynb` file is imported so you can view the cell operations. Continue to run each cell operations  within the imported `ML_Phishing_Detection.ipynb` file up to step 12. Cell operations should execute and return cell output values for various commands, including final prediction results for your phishing model.
 

### 2. Understanding the Steps

This section explains each step involved in building the model. The commands for these steps are included in your Jupyter Notebook. When running these commands, you will see the output of each cell operation executed. 

#### 2.1. Install Required Software and Libraries

Install Jupyter Notebook and necessary Python libraries like pandas, nltk, scikit-learn, and joblib. This step should already be done and revalidated 

#### 2.2. Import Libraries

Load all the necessary libraries into your notebook. These libraries offer various functions needed for data processing, text analysis, machine learning, and handling model files.

#### 2.3. Download NLTK Stopwords

Download a list of common words (stopwords) that don't contribute much meaning to text analysis.Removing these words helps focus on the more meaningful words in the emails, improving the accuracy of the model.

#### 2.4. Load the Dataset

Load the dataset containing emails into the notebook. Update the file path for the location of the dataset! This dataset is used to train and test the machine learning model. It includes emails labeled as either phishing or legitimate.

#### 2.5. Handle Missing Values

Check for and remove any missing data in the dataset. Missing data can cause errors in processing and analysis, so it's important to clean the data for accuracy.

#### 2.6. Preprocess Text Data

Convert all text to lowercase and remove stopwords to standardize the text. This standardizes the text, making it easier for the model to analyze without being distracted by differences in capitalization or common words.

#### 2.7. Convert Text to Numbers (Features)

Use the TF-IDF vectorizer to convert the text into numerical data. Machine learning models need numerical input to work. TF-IDF helps quantify the importance of words in each email, creating a numerical representation of the text.

#### 2.8. Split the Dataset

Divide the data into two parts: training data and testing data. The training data is used to teach the model, and the testing data is used to evaluate how well the model has learned.

#### 2.9. Train the Model

Use the training data to train a Logistic Regression model. The model learns patterns in the training data that help it distinguish between phishing and legitimate emails.

#### 2.10. Evaluate the Model

Test the model using the testing data and check its performance using metrics like precision, recall, and F1-score.This step shows how accurately the model can predict phishing and legitimate emails. Metrics help understand the model's strengths and areas for improvement.

#### 2.11. Save the Model and Vectorizer

Save the trained model and the TF-IDF vectorizer to files. Saving these allows you to reuse the model and vectorizer later without retraining, making predictions on new emails easier.

#### 2.12. Create a Prediction Function

Write a function to use the saved model to predict if a new email is phishing or legitimate. This function makes it easy to check new emails by inputting their text and getting a prediction with a probability score. Below is the expected output that you will see within your Jupyter Notebook. 



## Evaluation of Training Model
           precision    recall  f1-score   support

       0       0.96      1.00      0.98       500
       1       1.00      0.79      0.88       100

accuracy                           0.96       600

#### Explanation of Metrics

**Class 0 (Non-phishing emails):**

- **Precision:** 0.96 means 96% of the emails predicted as non-phishing are actually non-phishing.
- **Recall:** 1.00 means the model identified all actual non-phishing emails correctly.
- **F1-Score:** 0.98 is the balance between precision and recall.
- **Support:** 500 means there are 500 non-phishing emails in the test set.

**Class 1 (Phishing emails):**

- **Precision:** 1.00 means 100% of the emails predicted as phishing are actually phishing.
- **Recall:** 0.79 means the model identified 79% of the actual phishing emails correctly.
- **F1-Score:** 0.88 is the balance between precision and recall.
- **Support:** 100 means there are 100 phishing emails in the test set.

**Accuracy:** 0.96 (or 96%) means the model correctly predicted 96% of all emails (both phishing and non-phishing).

#### Sample Prediction Results 
```
Email: Congratulations! You've won a $1000 gift card. Click here to claim your prize.
Prediction: Phishing
Probability of Phishing: 95.23%

Email: Please review the attached document regarding last week's meeting.
Prediction: Legitimate
Probability of Phishing: 12.34%

Email: Important: Your account will be suspended unless you verify your information here.
Prediction: Phishing
Probability of Phishing: 93.67%

Email: Lunch meeting scheduled for tomorrow at 1 PM in the conference room.
Prediction: Legitimate
Probability of Phishing: 8.45%

Email: Your account has been compromised. Please reset your password immediately by clicking this link.
Prediction: Phishing
Probability of Phishing: 89.45%
```

#### Conclusion

These steps outline the process of building, training, and evaluating a machine learning model to detect phishing emails, ensuring the model is accurate and efficient for practical use. The project demonstrates the process of cleaning text data, extracting features, training a model, and making predictions, all within an interactive Jupyter Notebook environment.