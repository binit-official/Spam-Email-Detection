# Spam Email Detection using Machine Learning 


<!-- ABOUT THE PROJECT -->
## About The Project

Spam detection involves identifying and filtering out unwanted or unsolicited communications, such as emails or text messages. These messages, often sent by spammers or malicious entities, aim to advertise products, promote services, trick users into revealing personal information, or spread malware. To combat this, machine learning algorithms are commonly employed. These algorithms analyze message content, detecting patterns and features indicative of spam. By training on extensive datasets containing labeled examples of both spam and legitimate messages, these systems learn to differentiate between the two with high accuracy. Spam detection plays a crucial role for individuals and organizations by keeping inboxes free of unnecessary clutter, reducing the likelihood of phishing attempts, and enhancing overall cybersecurity. This repository includes a Python script that leverages several machine learning models to classify spam messages from legitimate ones, using a well-known spam email dataset for training and evaluation.
### Built With

 - NumPy
 
 - Pandas

 - Matplotlib

 - Seaborn

 - Sklearn
 
 <br>
 
 To install all the above mentioned libraries at a glance by executing the following command:
 
  ```sh
  pip install -r requirements.txt
  ```

<!-- GETTING STARTED -->


### Installation

1. Clone the repo

   ```sh
   gh repo clone binit-official/Spam-Email-Detection-main 
   ```
2. Install the required libraries

   ```sh
    pip install -r requirements.txt
   ```
3. Open and execute ```.ipynb``` file (After complete Execution you will get a ```.pkl``` file for project Deployment

# Dataset Description

I utilized the Email-Spam dataset available on Kaggle. The dataset comprises a collection of 5000+ emails, each having two features: Category and Message. 

```Message```   Message feature contains the actual text of the email. 

```Category```  The Category feature distinguishes between Spam and Ham emails

## Data Pre-processing

### Steps Performed:
1. **Dropping Unnecessary Columns**  
   Columns `'Unnamed: 2'`, `'Unnamed: 3'`, and `'Unnamed: 4'` are removed from the dataset as they are irrelevant.

2. **Handling Null Values**  
   Checked for missing values using the `isnull()` method to ensure data consistency.

3. **Binary Conversion of Categories**  
   - Converted the `'Category'` column into binary values:  
     - `'spam'` → `0`  
     - `'ham'` → `1`  
   - Printed the count of each category using the `value_counts()` method.

4. **Feature and Target Variables**  
   - **X**: Contains the `'Message'` column (input features).  
   - **Y**: Contains the `'Category'` column (output labels).

5. **Data Splitting**  
   Used `train_test_split()` from `sklearn.model_selection` to split the dataset into training and testing sets.

6. **Feature Extraction**  
   - Applied `TfidfVectorizer` from `sklearn.feature_extraction.text` to convert text into numerical features with the following parameters:  
     - `min_df=1`  
     - `stop_words='english'`  
     - `lowercase=True`  
   - Transformed training data with `fit_transform()` and testing data with `transform()`.  
   - Converted target variables (`Y_train` and `Y_test`) to integers.

---

## Model Training and Evaluation

Machine learning models are trained on the training data using the `fit()` method and tested using the `predict()` method. The performance of each model is evaluated using the following metrics:  
- **Accuracy**  
- **Precision**  
- **Recall**  
- **F1-Score**

### Algorithms Used:
- Logistic Regression  
- K Nearest Neighbors  
- Decision Trees  
- Random Forest  
- Stacking Model  

---

## Model Deployment

Deployment is implemented using **Streamlit**, an open-source Python library for creating interactive web applications.

### Deployment File:
The complete deployment code is in the file `Spam Classification Deployment.py`.

### To Run the Application:
Execute the following command in your terminal:  
```sh
python Spam Classification Deployment.py
```
  

