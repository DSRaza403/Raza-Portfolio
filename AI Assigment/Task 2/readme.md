
# **Task 2: RAG-Based Semantic Quote Retrieval and Structured QA with Model Training**

## **Objective**

The objective of Task 2 is to build a **Retrieval Augmented Generation (RAG)** system for semantic quote retrieval. The goal is to create a model capable of retrieving relevant quotes based on natural language queries. This task involves fine-tuning a model, implementing a RAG pipeline, evaluating the system's performance, and deploying an interactive **Streamlit** app.

## **Task Breakdown**

The task can be divided into the following main steps:

1. **Data Preparation**: Clean and preprocess the dataset (Abirate/english_quotes).
2. **Model Fine-Tuning**: Fine-tune a sentence embedding model on the dataset.
3. **RAG Pipeline**: Implement a RAG pipeline that retrieves relevant quotes based on input queries.
4. **RAG Evaluation**: Evaluate the system using one of the provided frameworks.
5. **Streamlit Application**: Create an interactive app where users can query the system and receive structured results.

## **Prerequisites**

Before running the code, ensure you have the following libraries installed:

- Python 3.x
- `transformers`
- `sentence-transformers`
- `streamlit`
- `faiss-cpu` (or `faiss-gpu` for GPU support)
- `datasets`
- `torch`
- `scikit-learn`


## **Project Structure**

```
├── streamlit_app.py                    # Streamlit App for querying the system
├── data_prep_model_finetuning.ipynb  # Data preparation and model fine-tuning notebook
├── rag_pipeline.ipynb        # RAG pipeline implementation notebook
├── rag_evaluation.ipynb      # RAG evaluation notebook
└── README.md                 # This documentation
```

## **Steps to Run the Code**

### 1. **Data Preparation**

- The dataset used for this task is the **Abirate/english_quotes** dataset, available on HuggingFace.
- In the **data_prep_model_finetuning.ipynb** notebook, the dataset is preprocessed to clean and tokenize the data. Missing values are handled, and the dataset is prepared for model fine-tuning.

### 2. **Model Fine-Tuning**

- A sentence embedding model (**MiniLM**) is fine-tuned on the quotes dataset.
- The **data_prep_model_finetuning.ipynb** notebook demonstrates how to fine-tune the model using the **sentence-transformers** library.
- The fine-tuned model is saved and can later be used in the RAG pipeline.

### 3. **Build the RAG Pipeline**

- The **rag_pipeline.ipynb** notebook implements the RAG pipeline.
- The fine-tuned model is used to encode the quotes dataset and index it using **FAISS** for efficient similarity search.
- A **Large Language Model (LLM)** such as **GPT-3.5** or **Llama2** is used to generate context-aware responses to the retrieved quotes based on user queries.

### 4. **RAG Evaluation**

- The **rag_evaluation.ipynb** notebook evaluates the performance of the RAG system.
- The system is tested against various queries, and the results are evaluated using frameworks like **RAGAS**, **Quotient**, or **Arize Phoenix**.
- Metrics like retrieval accuracy and response relevance are discussed and analyzed.

### 5. **Streamlit Application**

- An interactive **Streamlit** application is built using the **streamlit_app.py** file.
- Users can input natural language queries into the app, and the system retrieves the most relevant quotes, authors, tags, and summaries.
- The results are displayed in a structured JSON format, making it easy to understand the output.

To run the Streamlit app:

```bash
streamlit run streamlit_app.py
```
