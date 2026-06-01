# How LLMs Work


```text
Training Phase
────────────────────────────────────

Books + Websites + Code + Articles
                 │
                 ▼
      Learn Language Patterns
                 │
                 ▼
       Large Language Model


Inference Phase (Chatting)
────────────────────────────────────

User: "The capital of France is"
                 │
                 ▼
       Convert to Tokens
                 │
                 ▼
      Look at All Context
                 │
                 ▼
 Predict Most Likely Next Token
                 │
                 ▼
             "Paris"
                 │
                 ▼
      Predict Next Token Again
                 │
                 ▼
              "."
                 │
                 ▼
         Final Response
```

---

### The Core Idea

An LLM does one thing:
> Predict the next token based on previous tokens.

---

<br>
An LLM is a neural network trained on massive amounts of text that generates responses by repeatedly predicting the most likely token from the context it has been given.
</br>
