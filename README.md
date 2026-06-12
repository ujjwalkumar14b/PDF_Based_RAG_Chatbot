# PDF-Based RAG Chatbot
<video src="[https://github.com](https://github.com/ujjwalkumar14b/PDF_Based_RAG_Chatbot/blob/main/deployment.mp4)" width="100%" controls></video>

## Overview
This project implements a Retrieval-Augmented Generation (RAG) based chatbot that allows users to upload PDF documents and ask questions about their content. The application uses Hugging Face Embeddings for semantic representation, FAISS as the vector database for similarity search, and Llama 3 running locally through Ollama for answer generation. The system extracts text from uploaded PDFs, splits the content into manageable chunks, generates embeddings, stores them in a vector database, retrieves the most relevant chunks for a user query, and generates context-aware answers using a local Large Language Model (LLM).

## Project Structure
```
PDF_Based_RAG_Chatbot/
│
├── templates/
│   └── index.html                 # Frontend UI
├── uploads/                       # Uploaded PDF files
├── deployment.mp4                 # App preview
├── requirements.txt               # Project dependencies
├── app.py                         # Flask application
└── README.md
```


## Installation
```
git clone https://github.com/ujjwalkumar14b/PDF_Based_RAG_Chatbot.git
cd PDF_Based_RAG_Chatbot
pip install -r requirements.txt
python app.py
```

## RAG Pipeline
### 1. Importing Libraries and PDF Collection
* Flask
* PyPDF
* LangChain
* FAISS
* Hugging Face Embeddings
* Ollama (Llama 3)
* Uploaded PDF Documents

### 2. PDF Text Extraction
The system extracts textual content from uploaded PDF files using PyPDF.
* Read multiple PDF documents
* Extract text page by page
* Combine content into a single text corpus
  
### 3. Text Chunking
Large documents are divided into smaller chunks to improve retrieval performance.
* RecursiveCharacterTextSplitter
* Chunk Size: 1000
* Chunk Overlap: 200

### 4. Embedding Generation
Semantic vector representations are generated using sentence-transformers/all-MiniLM-L6-v2
These embeddings capture the contextual meaning of document content.

### 5. Vector Database Creation
FAISS is used for efficient similarity search.
* Store document embeddings
* Fast retrieval of relevant chunks
* Scalable vector search
  
### 6. Similarity Search
When a user asks a question:
* Query embedding is generated
* Similar chunks are retrieved from FAISS
* Top relevant document sections are selected

### 7. Answer Generation Using Llama 3
Retrieved document chunks are provided as context to the local Llama 3 model running through Ollama. Features include:
* Context-aware responses
* Local inference
* No OpenAI API required
* Privacy-friendly document processing

### 8. Deployment
* Web Application using HTML, CSS, Bootstrap, Flask
* The application can be deployed on Render,AWS EC2, Heroku (if configured)


## Author
Ujjwal Kumar
GitHub: [https://github.com/ujjwalkumar14b](https://github.com/ujjwalkumar14b)


## License
This project is open-source and available under the MIT License.
