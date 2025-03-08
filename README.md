
# **CardClarity AI: A Credit Card Assistant**

## **Overview**
CardClarity AI is an intelligent credit card assistant that leverages **Retrieval-Augmented Generation (RAG)** techniques to provide context-aware answers to user queries. By integrating **LangChain**, **Hugging Face Transformers**, and **Groq LLM**, this application retrieves relevant information from multiple sources and generates precise, context-based answers.

The assistant is designed to simplify credit card-related queries, offering users clarity and actionable insights by processing data from user-provided URLs.

---

## **Features**
- **Multi-Source Document Retrieval:** Retrieves relevant information from multiple sources using FAISS vector stores.
- **Generative AI Integration:** Uses Groq LLM to generate accurate, context-aware responses.
- **Multi-Query Enhancement:** Generates multiple variations of user queries to improve retrieval accuracy.
- **Document Chunking:** Splits large documents into manageable chunks for efficient embedding and retrieval.
- **Context-Based Responses:** Ensures answers are strictly derived from the provided context, avoiding external knowledge.

---

## **Technologies Used**

### **Programming Languages:**
- Python
### **Frameworks & Libraries:**
- [Streamlit](https://streamlit.io/) for the user interface
- [LangChain](https://www.langchain.com/) for RAG pipeline implementation
- [Hugging Face Transformers](https://huggingface.co/transformers/) for embeddings
- [FAISS](https://faiss.ai/) for vector-based similarity search
- [Groq LLM](https://groq.com/) for generative AI

### **Other Tools:**
- JSON for saving retrieved documents
- PostgreSQL (optional) for data storage
- AWS Lambda (optional) for scalable deployment

---

## **File Descriptions**

1. **`credit_card_assistant_app.py`:** Main Streamlit application that serves as the user interface for the assistant.
2. **`vectorstore_service.py`:** Handles vector store creation and retrieval using FAISS.
3. **`multi_query_generation.py`:** Implements multi-query generation techniques using Groq LLM to enhance document retrieval accuracy.
4. **`data_chunk_splitter.py`:** Splits large documents into smaller chunks for embedding and processing.
5. **`rag_assistant.py`:** Core logic of the Retrieval-Augmented Generation (RAG)-based assistant, including query processing and response generation.
6. **`requirements.txt`:** Lists all dependencies required to run the project.

---

## **Installation**

### Prerequisites:
1. Python 3.8 or higher installed on your system.
2. An OpenAI API key or Groq API key (for LLM integration).
3. Install PostgreSQL if you plan to use it as a database.

### Steps:
1. Clone the repository:
   ```bash
   git clone https://github.com/Bhavank815/CreditWise-AI/tree/main
   cd CardClarityAI
   ```

2. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Set up environment variables:
   - Create a `.env` file in the project directory with the following keys:
     ```
     GROQ_API_KEY=your_groq_api_key_here
     ```

4. Run the application:
   ```bash
   python credit_card_assistant_app.py
   ```

---

## **How It Works**

1. Users enter URLs containing credit card-related information into the sidebar of the Streamlit application.
2. The assistant processes these URLs by:
   - Loading documents from the URLs using `WebBaseLoader`.
   - Splitting documents into chunks using `RecursiveCharacterTextSplitter`.
   - Creating embeddings with Hugging Face models and storing them in FAISS vector stores.
3. When a user submits a query, the assistant:
   - Generates alternative query perspectives using `MultiQueryTechnique`.
   - Retrieves relevant documents from the vector store.
   - Uses Groq LLM with strict context-based prompts to generate accurate answers.
4. The assistant displays the answer along with sources used for generating it.

---

## **Usage Example**

1. Launch the application:
   ```bash
   python credit_card_assistant_app.py
   ```
2. Enter URLs containing credit card details in the sidebar (e.g., terms and conditions pages, FAQs).
3. Submit a query like:
   ```
   What is the cashback policy for this credit card?
   ```
4. View the generated answer along with its sources.

---

## **Project Structure**

```
CardClarityAI/
├── credit_card_assistant_app.py      # Main Streamlit application
├── vectorstore_service.py           # Vector store creation and retrieval logic
├── multi_query_generation.py        # Multi-query generation techniques
├── data_chunk_splitter.py           # Document chunking logic
├── rag_assistant.py                 # Core RAG assistant logic
├── requirements.txt                 # Project dependencies
└── README.md                        # Project documentation
```

---

## **Future Enhancements**

1. Add support for additional document formats (e.g., PDFs, Word files).
2. Integrate more advanced LLMs like GPT-4 or domain-specific models.
3. Enhance UI/UX with more interactive features in Streamlit.
4. Deploy on AWS or Google Cloud for scalability.

---

## **License**
This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.


