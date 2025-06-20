
## **Evaluation Results Discussion**

### **Model Fine-Tuning**
The fine-tuned sentence embedding model demonstrated good performance in understanding the context of user queries and retrieving relevant quotes from the dataset. The fine-tuning process involved using transformer models like **DistilBERT** or **MiniLM**, which were effective for this task.

### **RAG Retrieval**
The RAG pipeline retrieved relevant quotes accurately for most queries. However, more complex queries involving multiple tags or authors showed some limitations in retrieval performance. There is room for improvement in handling multi-hop or complex queries.

### **RAG Evaluation**
The system was evaluated using the **RAGAS** framework. The evaluation revealed that while the retrieval process was robust for simple queries, it could be improved for more complex or multi-hop queries.

### **Streamlit Application**
The Streamlit app provided an intuitive user interface for querying the system. It returned structured responses, which included quotes, authors, tags, and summaries, making it easy for users to understand the results. The app worked seamlessly, allowing users to interact with the RAG system effortlessly.

## **Challenges Faced**

- **Fine-Tuning the Model**: Fine-tuning a model to handle diverse types of queries from the dataset required careful data curation and parameter tuning.
- **Multi-hop Queries**: Handling multi-hop queries (e.g., queries involving multiple tags or authors) was challenging. The RAG pipeline needed adjustments to better manage complex queries.
- **Data Handling**: Ensuring data cleanliness and consistency, especially in handling missing values and noisy text, was critical for model performance.

## **Conclusion**

This project demonstrates the use of a **Retrieval Augmented Generation (RAG)** system to perform semantic quote retrieval and structured question answering. The RAG pipeline performs well for basic queries but requires further fine-tuning to handle complex, multi-hop queries. The Streamlit app provides an easy-to-use interface for interacting with the system, and the project showcases a successful implementation of RAG for quote retrieval.
