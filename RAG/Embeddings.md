# Embeddings

## What are Embeddings?

Embeddings are numerical vector representations of data such as text, images, or audio.

They convert human-readable information into numbers that machines can process and compare.

---

## Why are Embeddings Needed?

Computers cannot understand text directly.

Example:

```text
Artificial Intelligence
Machine Learning
Football
```

Humans know that Artificial Intelligence and Machine Learning are related concepts.

Embeddings allow computers to capture this semantic similarity mathematically.

---

## How Embeddings Work

```text
Text
 ↓
Embedding Model
 ↓
Vector
```

Example:

```text
"What is Artificial Intelligence?"
 ↓
[-0.028, -0.003, 0.022, ...]
```

In my project, Gemini generated a vector with 3072 dimensions.

---

## Semantic Similarity

Similar concepts produce similar vectors.

Example:

```text
Artificial Intelligence
Machine Learning
```

These vectors are closer together than:

```text
Artificial Intelligence
Football
```

---

## Embeddings in RAG

```text
PDF
 ↓
Chunks
 ↓
Embeddings
 ↓
Vector Database
 ↓
Retriever
 ↓
LLM
```

Each chunk is converted into a vector and stored in a vector database.

When a user asks a question:

```text
Question
 ↓
Embedding
 ↓
Similarity Search
 ↓
Relevant Chunks
```

The system retrieves chunks with vectors closest to the question vector.

---

## Common Embedding Models

* Gemini Embeddings
* OpenAI Embeddings
* BERT Embeddings
* Sentence Transformers
* Cohere Embeddings

---

## Applications

* Semantic Search
* RAG Systems
* Recommendation Systems
* Document Retrieval
* Question Answering

---

## Key Takeaways

* Embeddings convert text into vectors.
* Similar meanings produce similar vectors.
* Embeddings enable semantic search.
* Vector databases store embeddings for efficient retrieval.
* Embeddings are a core component of modern RAG systems.
