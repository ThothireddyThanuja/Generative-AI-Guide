## Context Window

A **Context Window** is the maximum amount of information an LLM can **consider in a single request/conversation context**.

It determines how much **input + conversation history + other context + generated output** the model can handle within one request.

### Simple Example

Suppose an LLM has a context window of **100,000 tokens**.

Conceptually:

```text
Context Window = 100,000 tokens

Input / Context
      +
Output
      ↓
Must fit within
100,000 tokens
```

For example:

```text
User Input       → 20,000 tokens
Conversation     → 30,000 tokens
Documents        → 40,000 tokens
Output           → 10,000 tokens
                    ────────────
Total            → 100,000 tokens
```

The exact limits and accounting can vary by model/provider.

### Why is Context Window Important?

The context window determines how much information the model can work with **at one time**.

For example, if you provide a large document:

```text
Large Document
      ↓
Tokenization
      ↓
Tokens
      ↓
Context Window
      ↓
LLM processes the available context
      ↓
Response
```

If the input is larger than the model's supported context window, the entire input cannot be processed in that request. The application may need to **truncate, summarize, chunk, or otherwise reduce the context**.

### Context Window vs Memory

These are not the same.

**Context Window**
→ Information available to the model for the current request.

**Long-term Memory**
→ Information stored separately and potentially retrieved and added to a future request.

For example:

```text
Previous conversation
        ↓
Relevant information retrieved
        ↓
Added to current context
        ↓
LLM
```

### Important Correction

Instead of defining it as:

> "How much input size and output size an LLM can handle at a single request"

A better definition is:

> **Context window is the maximum number of tokens that an LLM can consider within a single request context, including the input/context and the generated output, subject to the model's specific limits.**

### Interview Answer

> **A context window is the maximum number of tokens an LLM can process as context for a request. It includes the user's input, relevant conversation history or other supplied context, and the model's generated output.**

### Easy way to remember

**Context Window = How much information the model can see/work with at one time.**

And remember: **context window is measured in tokens, not simply words or characters.**
