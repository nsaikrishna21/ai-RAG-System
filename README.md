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
