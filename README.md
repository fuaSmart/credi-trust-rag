# CrediTrust RAG System

## Project Overview
This project implements a Retrieval Augmented Generation (RAG) system to answer questions about credit card customer complaints. It leverages vector embeddings for efficient document retrieval and a fine-tuned Large Language Model (LLM) for context-aware answer generation.

## Features
- **Data Processing:** Handles PDF/CSV/TXT complaint data, chunks it, and generates embeddings.
- **Vector Store:** Utilizes FAISS for fast similarity search of relevant complaint excerpts.
- **LLM Integration:** Uses TinyLlama-1.1B-Chat via Hugging Face Transformers and LangChain for natural language understanding and generation.
- **RAG Pipeline:** Combines document retrieval with LLM generation to answer user queries based on provided context.
- **Qualitative Evaluation:** Framework for assessing the quality and relevance of generated answers.
- **Interactive Interface:** (To be implemented in Task 4) User-friendly chat application for interaction.

## Setup & Installation

1.  **Clone the repository:**
    ```bash
    git clone [YOUR_REPO_LINK]
    cd credi-trust-rag
    ```
    *(Replace `[YOUR_REPO_LINK]` with the actual URL of your GitHub repository)*
2.  **Create and activate a Python virtual environment:**
    ```bash
    python3 -m venv venv
    source venv/bin/activate
    ```
3.  **Install required Python libraries:**
    ```bash
    pip install -r requirements.txt # If you've created this file
    # OR manually install key libraries:
    pip install torch==2.3.0 transformers==4.42.3 langchain==0.2.7 faiss-cpu==1.8.0 sentence-transformers==2.7.0 accelerate==0.31.0 unstructured==0.14.4 pytesseract==0.3.10 Pillow==10.3.0 tiktoken==0.7.0 fastembed==0.2.7
    # Note: Tesseract OCR (for PDF/image text extraction) may need to be installed separately on your OS.
    # Example for Ubuntu: sudo apt-get update && sudo apt-get install tesseract-ocr
    ```

## Usage

1.  **Prepare Data:** Place your raw credit card complaint documents (PDFs, CSVs, TXTs) into the `data/` directory.
2.  **Run Data Processing & Embedding Creation:** Execute your `01_data_preprocessing.ipynb` and `02_embedding_creation.ipynb` notebooks sequentially to process data and build the vector store.
3.  **Run RAG Pipeline:** Execute your `03_rag_pipeline.ipynb` notebook to set up the LLM and the RAG chain. Test with queries.
4.  **Launch Interactive Interface:** (Once Task 4 is complete) Run `python app.py` from the project root.

## Project Structure
- `data/`: Stores raw complaint documents.
- `vector_store/`: Contains the FAISS vector index.
- `notebooks/`: Jupyter notebooks for development (`01_data_preprocessing.ipynb`, `02_embedding_creation.ipynb`, `03_rag_pipeline.ipynb`).
- `src/`: (Optional) Python modules for modular code.
- `app.py`: (For Task 4) The main script for the interactive Gradio/Streamlit application.
- `requirements.txt`: Lists Python dependencies for easy installation.