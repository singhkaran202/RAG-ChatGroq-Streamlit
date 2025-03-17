# RAG-ChatGroq-Streamlit

A Retrieval-Augmented Generation (RAG) application that uses ChatGroq LLM, Ollama embeddings, and FAISS vector search to provide accurate responses based on document context.

## Overview

This project demonstrates how to build a document similarity search application using Streamlit and LangChain. The application loads web content, splits it into chunks, creates vector embeddings, and then answers user queries by retrieving relevant document sections and generating responses using the powerful Llama 3.3 70B model via Groq's API.

## Features

- Web content loading and preprocessing
- Document chunking with RecursiveCharacterTextSplitter
- Vector embedding generation with Ollama's Llama 3.2
- Efficient vector search using FAISS
- Retrieval-Augmented Generation (RAG) with ChatGroq
- Interactive Streamlit UI
- Performance timing for response generation
- Expandable view of relevant document chunks

## Getting Started

### Prerequisites

- Python 3.8+
- Groq API key
- Ollama installed locally (for embeddings)
- Required Python packages (see requirements.txt)

### Installation

1. Clone the repository:
```
git clone https://github.com/yourusername/RAG-ChatGroq-Streamlit.git
cd RAG-ChatGroq-Streamlit
```
2. Install dependencies:
```
pip install -r requirements.txt
```
3. Set up environment variables:
```
cp .env.example .env
```
Then add your Groq API key to the `.env` file.

4. Ensure Ollama is running locally with the Llama 3.2 model:
```
ollama pull llama3.2
```
### Usage

Start the Streamlit application:
```
streamlit run app.py
```
This will open the application in your default web browser where you can:
1. Enter a query in the input field
2. Receive an answer based on the context of the loaded documents
3. Expand the "Document Similarity Search" section to see which document chunks were used to generate the answer

## How It Works

1. The application loads content from the LangChain Smith documentation
2. The text is split into manageable chunks
3. Each chunk is converted to a vector embedding using Ollama's Llama 3.2
4. When a user submits a query, the application:
   - Converts the query to an embedding
   - Finds the most similar document chunks using FAISS
   - Sends the query and relevant document chunks to ChatGroq's Llama 3.3 70B model
   - Displays the response and relevant document chunks to the user

## Customization

You can modify the application by:
- Changing the `WebBaseLoader` URL to load different content
- Adjusting the `chunk_size` and `chunk_overlap` parameters
- Trying different embedding models
- Modifying the prompt template for different response styles
