# Chunking

## What is Chunking?

Chunking is the process of splitting large documents into smaller pieces called chunks.

Large Language Models (LLMs) have context window limitations and cannot efficiently process very large documents at once. Chunking helps break documents into manageable sections.

---

## Why is Chunking Needed?

Consider a research paper with 100 pages.

```text
Research Paper
      ↓
Entire Document
```

Sending the entire document to an LLM is inefficient and may exceed context limits.

Instead:

```text
Research Paper
      ↓
Chunk 1
Chunk 2
Chunk 3
...
```

The document is divided into smaller pieces that can be processed and retrieved efficiently.

---

## Chunk Overlap

Chunk overlap preserves context between chunks.

Example:

```text
Chunk 1:
Artificial Intelligence is transforming industries.

Chunk 2:
transforming industries by enabling automation.
```

The overlapping words help maintain continuity and reduce information loss.

---

## Chunking in RAG

```text
PDF
 ↓
Chunking
 ↓
Chunks
 ↓
Embeddings
 ↓
Vector Database
```

Chunking is the first major preprocessing step in a Retrieval-Augmented Generation (RAG) pipeline.

---

## Chunking Methods

* Fixed-size chunking
* Recursive chunking
* Semantic chunking
* Sentence-based chunking

---

## LangChain Example

```python
from langchain_text_splitters import RecursiveCharacterTextSplitter

splitter = RecursiveCharacterTextSplitter(
    chunk_size=500,
    chunk_overlap=100
)

chunks = splitter.split_documents(docs)
```

---

## Key Takeaways

* Chunking splits large documents into smaller sections.
* It helps overcome context window limitations.
* Overlap preserves context between chunks.
* Chunking is an essential step in RAG systems.
