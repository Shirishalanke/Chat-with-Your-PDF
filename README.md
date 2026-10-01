# 📄 Chat with Your PDF

Upload a PDF and ask questions about it using **Retrieval-Augmented Generation (RAG)**.

The application extracts text from the uploaded PDF, splits it into chunks, generates embeddings using `all-MiniLM-L6-v2`, stores them in **ChromaDB**, retrieves the most relevant chunks for a question, and sends the retrieved context to a local **Ollama LLM** to generate an answer.

## 🚀 Live App

👉 **[Chat with Your PDF](https://chat-with-your-pdf-2waym8rlcekhhu3rzwacej.streamlit.app/)**

## ✨ Features

* 📄 Upload PDF documents
* ✂️ Automatically split PDF text into chunks
* 🧠 Generate semantic embeddings
* 🗄️ Store and search embeddings using ChromaDB
* 🔎 Retrieve the most relevant information from the PDF
* 🤖 Generate answers using Ollama
* 💬 Interactive Streamlit interface
* 🏠 Run the complete application locally

## 🔄 How It Works

```text
             PDF Upload
                  │
                  ▼
          Extract PDF Text
                  │
                  ▼
           Split into Chunks
                  │
                  ▼
        Generate Embeddings
       (all-MiniLM-L6-v2)
                  │
                  ▼
            ChromaDB
         Vector Storage
                  │
                  ▼
          User's Question
                  │
                  ▼
       Generate Question Embedding
                  │
                  ▼
      Retrieve Relevant PDF Chunks
                  │
                  ▼
          Ollama LLM (llama3.2)
                  │
                  ▼
           Generated Answer
```

## 🛠️ Tech Stack

| Technology                | Purpose                 |
| ------------------------- | ----------------------- |
| **Python**                | Application development |
| **Streamlit**             | Web interface           |
| **pypdf**                 | PDF text extraction     |
| **Sentence Transformers** | Text embeddings         |
| **all-MiniLM-L6-v2**      | Embedding model         |
| **ChromaDB**              | Vector database         |
| **Ollama**                | Local LLM inference     |
| **llama3.2**              | Language model          |

## 📁 Project Structure

```text
chat-with-your-pdf/
│
├── app.py
├── requirements.txt
├── README.md
└── .gitignore
```

## ⚙️ Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/your-username/chat-with-your-pdf.git
cd chat-with-your-pdf
```

### 2. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 3. Install Ollama

Download and install Ollama from:

https://ollama.com/

Then download the `llama3.2` model:

```bash
ollama pull llama3.2
```

### 4. Start Ollama

```bash
ollama serve
```

Keep Ollama running in the background.

### 5. Start the Streamlit application

```bash
streamlit run app.py
```

The application will normally be available at:

```text
http://localhost:8501
```

## 📦 Requirements

Your `requirements.txt` should include the packages required by the application, for example:

```text
streamlit
pypdf
sentence-transformers
chromadb
```

Ollama is installed separately because it runs as a local application rather than as a Python package.

## 🤖 Ollama Configuration

This project uses:

```text
Model: llama3.2
```

Make sure the model is available before running the application:

```bash
ollama list
```

If `llama3.2` is not listed, run:

```bash
ollama pull llama3.2
```

## ⚠️ Important Note About the Live App

The Streamlit deployment provides the application interface, but **answer generation requires Ollama**.

Ollama is designed to run locally, so the complete question-answering workflow works when the application is run on a machine where Ollama is installed and running.

For local use:

```bash
ollama serve
streamlit run app.py
```

## 💡 Example Questions

After uploading a PDF, you can ask questions such as:

```text
What is this document about?
```

```text
What are the main points discussed in the document?
```

```text
Summarize the document.
```

```text
What are the key findings?
```

```text
Explain the section about [topic].
```

```text
What are the advantages mentioned in the document?
```

## 🔐 Privacy

When running the application locally, PDF processing, vector storage, and LLM inference can be performed on your own machine.

No external LLM API is required for answer generation when using Ollama locally.

## 🚀 Future Improvements

* 📚 Support multiple PDFs
* 💾 Persistent document collections
* 📝 Conversation history
* 📌 Source citations for generated answers
* 🔍 Improved chunking strategies
* 🎨 Enhanced user interface
* ☁️ Cloud-based LLM support
* 📊 Document management

## 👨‍💻 Author

Developed as a PDF question-answering application using **RAG, ChromaDB, Sentence Transformers, Streamlit, and Ollama**.

---

⭐ If you find this project useful, consider giving the repository a star!
