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

## Qdrant DB - Storing + Retriving the data 

The Qdrant DB is a vector database that is used to store and search vectors. It is a service that persists to disk, filters by metadata, and answers many queries at once.

### Qdrant Demo

The Qdrant demo is a script that demonstrates how to use the Qdrant DB. It creates a collection, adds vectors and metadata to it, and searches for vectors using a query vector.

### Qdrant Store

The Qdrant store is a class that stores vectors and metadata in Qdrant and searches by cosine similarity. It uses the Qdrant client to create a collection, add points to it, and search for points using a query vector.

## Running the App with Uvicorn

To run the app with Uvicorn, use the following command:

```bash
uvicorn app.main:app --port 8000
```

This will start the Uvicorn server and make the app available at `http://localhost:8000`.

You can use the semantic search functionality of the app by sending a GET request to `http://localhost:8000/search` with a query parameter. For example:

```javascript
http://localhost:8000/search?query=How+will+the+city+pay+for+the+new+sports+venue?
```

This will return a list of search results, including the relevance score and the text of the matching chunks.

## Commands

- `python build_index.py` to build the index
- `python search.py` to search for vectors
- `uvicorn app.main:app --port 8000` to start the app
- `docker compose up -d qdrant` to start the Qdrant DB
