# LangChain Intr0

---

## What I Built

Created a simple LangChain agent using Groq's Llama 3.3 70B model.

```python
agent = create_agent(
    model=llm,
    tools=[get_weather, get_population],
    system_prompt="You are a helpful assistant."
)
```

---

## Key Concepts Learned

### 1. Agent = LLM + Tools + Loop

An agent is not just an LLM.

The agent workflow is:

User → LLM → Tool Call → Tool Result → LLM → Final Answer

The model decides when and how to use tools.

---

### 2. Tool Calling

A Python function can become a tool.

Example:

```python
def get_weather(city: str) -> str:
    """Get weather for a city."""
    return f"The weather in {city} is sunny."
```

The docstring helps the model understand what the tool does.

---

### 3. Agents Can Call Tools Multiple Times

When asked about Kashmir, the model called:

* get_weather("Kashmir")
* get_weather("Srinagar")
* get_weather("Jammu")

even though I only asked one question.

The model was planning and gathering additional information.

---

### 4. Multiple Tools Can Be Registered

```python
tools=[get_weather, get_population]
```

The model chooses which tool to use based on the question.

---

### 5. Tool Calls Are Visible

The agent output contains:

* HumanMessage
* AIMessage
* ToolMessage

Example flow:

HumanMessage
↓
AIMessage (tool call)
↓
ToolMessage (tool result)
↓
AIMessage (final answer)

---

### 6. Models Do Not Always Trust Tools

Experiment:

```python
def get_population(city: str) -> str:
    return "The population is 99999."
```

The tool returned:

```text
The population is 99999.
```

But the model answered:

```text
The population of New York is approximately 8.4 million.
```

This means:

* Tool execution worked.
* The model ignored the tool output.
* Models may override tool results using their own knowledge.

---

### 7. Agent Debugging Is Different

Traditional debugging:

* Fix code.

Agent debugging:

* Understand why the model chose a tool.
* Understand why the model ignored a tool.
* Understand why the model made a particular plan.

---

## Biggest Takeaway

The tool is not the smart part.

The model is the smart part.

Tools only provide capabilities. The LLM decides:

* Which tool to use
* When to use it
* How many times to use it
* Whether to trust the result

---
