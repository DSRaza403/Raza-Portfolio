

# **Task 1: Machine Learning Pipeline for Classifying Customer Support Tickets**

## **Objective**

The objective of Task 1 is to develop a machine learning pipeline that classifies customer support tickets based on their issue type and urgency level, and extracts key entities such as product names, dates, and complaint keywords. The provided dataset includes anonymized customer support ticket data, and the goal is to clean, preprocess, and build machine learning models to predict issue type and urgency level, as well as extract key entities from the ticket text.

## **Task Breakdown**

The task is divided into the following steps:

1. **Data Preparation**: Cleaning and preprocessing the provided customer support ticket dataset.
2. **Feature Engineering**: Creating meaningful features using traditional NLP techniques.
3. **Multi-Task Learning**: Building two separate classification models: one for predicting the issue type and one for predicting the urgency level.
4. **Entity Extraction**: Extracting key entities from the ticket text (product names, dates, and complaint keywords).
5. **Integration**: Building a function to return predictions (issue type, urgency level) and extracted entities for raw ticket text.
6. **Gradio Interface (Optional)**: Creating an interactive Gradio interface to allow users to input raw ticket text and see the predicted outputs.

## **Prerequisites**

Before running the code, ensure that the following libraries are installed:

- Python 3.x
- `pandas`
- `nltk`
- `scikit-learn`
- `gradio` (for the optional Gradio interface)

## **Project Structure**

```
├── AI Assignment Task 1.ipynb   # Jupyter notebook for data preparation, feature engineering, and model building
└── README.md                    # This documentation
```

## **Steps to Run the Code**

### 1. **Data Preparation**

The dataset, `ai_dev_assignment_tickets_complex_1000.xlsx`, is loaded and preprocessed in the notebook. Key preprocessing steps include:

- **Text Normalization**: Converts text to lowercase and removes punctuation.
- **Tokenization**: Splits the text into individual words.
- **Stopword Removal**: Removes common words like "the", "is", etc., to focus on meaningful words.
- **Lemmatization**: Reduces words to their base form (e.g., "running" to "run").

Additionally, missing values are handled as follows:

- Missing `ticket_text` is removed from the dataset.
- Missing `urgency_level` is filled with the value `'Medium'`.
- Missing `issue_type` is filled with the value `'unspecified'`.

### 2. **Feature Engineering**

- **Bag-of-Words / TF-IDF**: These methods are used to extract features from the text, which will be used for classification models.
- **Additional Features**: Additional features such as ticket length and sentiment score are created to assist the model.

### 3. **Multi-Task Learning**

Two separate classification models are trained:

1. **Issue Type Classifier**: A multi-class classification model that predicts the issue type (e.g., "Payment issue", "Product inquiry").
2. **Urgency Level Classifier**: A multi-class classification model that predicts the urgency level (e.g., Low, Medium, High).

These models are trained using traditional machine learning algorithms like **Logistic Regression**, **SVM**, or **Random Forest**.

### 4. **Entity Extraction**

Using traditional NLP techniques, key entities are extracted from the `ticket_text`:

- **Product Names**: Extracted from a provided product list or using regex/rule-based methods.
- **Dates**: Dates mentioned in the text are extracted using date recognition techniques.
- **Complaint Keywords**: Keywords such as "broken", "late", and "error" are identified using keyword matching.

### 5. **Integration**

A function is created to take raw ticket text as input and return:

- Predicted `issue_type`
- Predicted `urgency_level`
- Extracted entities (in JSON/dictionary format)

### 6. **Gradio Interface (Optional)**

An interactive **Gradio** app is built (optional step) where users can:

- Input raw ticket text.
- See the predicted issue type, urgency level, and extracted entities as output.

To run the Gradio app, use the following command:

```bash
gradio.Interface(fn=your_function, inputs="text", outputs=["text", "json"]).launch()
```

## **Conclusion**

This notebook demonstrates how to preprocess customer support tickets, engineer meaningful features, train multi-task classification models, and extract key entities from ticket texts. The system can classify tickets into issue types and urgency levels, while also extracting important details like product names and complaint keywords. The optional Gradio interface allows users to interact with the model in real-time.
