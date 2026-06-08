# FAISS Vector Search Demo

This folder contains a simple FAISS-based embedding search demo using Python.

## Contents

- `faiss.ipynb` - Jupyter notebook with the full workflow:
  - chunking sample text
  - generating embeddings via an API
  - creating a FAISS index (`IndexFlatL2`)
  - searching the index for a query embedding
- `faiss_index.faiss` - persisted FAISS index file created by the notebook

## Requirements

- Python 3.8+ (or compatible)
- `faiss-cpu`
- `numpy`
- `requests`

## Setup

1. Open `faiss.ipynb` in Jupyter or VS Code.
2. Install dependencies if needed:

```bash
pip install faiss-cpu numpy requests
```

3. Run notebook cells in order.

## Notes

- The notebook currently uses an external embedding API endpoint.
- FAISS stores vector embeddings in the same order as `chunks`, so index lookups must match that order.
- If the notebook is rerun, make sure the FAISS index is recreated before adding embeddings again to avoid duplicate vectors.

## Usage

- Use the notebook to generate chunk embeddings and build a FAISS index.
- Run the query cell to search the index and inspect the returned chunk indices.
- If you see an out-of-range chunk index, recreate the index and re-add the embeddings.
