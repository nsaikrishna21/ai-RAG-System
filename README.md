This is a repository for the ai-RAG-System project.

## Prerequisites

- Python 3.x
- pip
- virtualenv

## Installation

1. Create a new virtual environment using `python -m venv myenv`
2. Activate the virtual environment using `myenv\Scripts\activate`
3. Install the required packages using `pip install -r requirements.txt`

## Chunking

The chunking logic is implemented in the `rag/chunk.py` file. It uses the `langchain_text_splitters` library to split the documents into embedding-ready pieces.

## Build Chunks

The `build_chunks.py` file is used to build the chunks. It uses the `ingest_folder` function from `rag/ingest.py` to ingest the documents and then splits them into chunks using the `chunk_documents` function from `rag/chunk.py`.

## Explore

The `explore.py` file is used to explore the chunking behavior. It uses the `ingest_folder` function from `rag/ingest.py` to ingest the documents and then splits them into chunks using the `naive_chunk` function from `rag/chunk.py`.

## Vector Search and Indexing

### Vector Store

The vector store is implemented using the Faiss library. It stores the indexed vectors and chunks in the index.faiss and index.faiss.chunks.json files respectively.

### Embedding

The embedding functionality is implemented in the rag/embed.py file. It uses the Hugging Face Transformers library to embed the text into vectors.

### Search

The search functionality is implemented in the search.py file. It uses the Faiss library to search for vectors in the index.

### Environment Variables

The environment variables for the vector store and search are defined in the.env.example file. These variables include the path to the index files and the chunk size.

## Commands

* `python build_index.py` to build the index
* `python search.py` to search for vectors
