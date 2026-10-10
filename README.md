# PDF RAG Assistant

My first RAG chatbot, its not a production-ready project

A Retrieval-Augmented Generation (RAG) chatbot that answers questions based on local PDF documents using LangChain, FAISS, and OpenAI.

## Features

- Load PDF documents from a local directory using Unstructured.
- Split documents into overlapping text chunks.
- Generate vector embeddings using OpenAI.
- Store document embeddings in a FAISS vector store.
- Retrieve relevant context using similarity search with a score threshold.
- Generate context-grounded answers using an OpenAI language model.
- Experimental source citations.

## Tech Stack

- **Python** — Core programming language
- **LangChain** — RAG pipeline orchestration
- **Unstructured** — PDF document processing
- **FAISS** — Vector similarity search
- **OpenAI Embeddings** — `text-embedding-3-small`
- **OpenAI LLM** — `gpt-4.1-nano`

## Getting Started

### 1. Clone the repository

```bash
git clone https://github.com/USERNAME/pdf-rag-assistant.git
cd pdf-rag-assistant
```

Replace `USERNAME` with your GitHub username.

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate the environment on Windows:

```powershell
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```bash
python -m pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root and add your OpenAI API key:

```env
OPENAI_API_KEY=your_api_key_here
```

### 5. Add PDF documents

Place your PDF files inside the `papers/` directory.

### 6. Run the chatbot

```bash
python chatbot.py
```

Enter a question when prompted. The chatbot will retrieve relevant information from the PDF documents and generate an answer.

## How It Works

1. **Document Loading:** PDF files are loaded using `DirectoryLoader` and `UnstructuredFileLoader`.
2. **Text Splitting:** Documents are divided into overlapping chunks using `RecursiveCharacterTextSplitter`.
3. **Embedding:** Each chunk is converted into a vector using OpenAI's `text-embedding-3-small`.
4. **Vector Storage:** Embeddings are stored in FAISS.
5. **Retrieval:** Relevant chunks are retrieved using similarity search with a score threshold.
6. **Answer Generation:** Retrieved context is passed to `gpt-4.1-nano` to generate an answer.

## Current Limitations

- Command-line interface only.
- FAISS index is rebuilt on each execution.
- Source citation accuracy is still being improved.
- No conversational memory.
- Requires an OpenAI API key and internet connection.

## Future Improvements

- Implement accurate page-level citations.
- Add persistent FAISS vector storage.
- Support conversational history.
- Develop a web-based chat interface.
- Evaluate retrieval and answer quality.