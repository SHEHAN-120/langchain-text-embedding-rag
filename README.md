# LangChain RAG Pipeline with OpenAI and Chroma

This project demonstrates a Retrieval-Augmented Generation (RAG) pipeline using LangChain, OpenAI Embeddings, and Chroma as the vector store. It loads documents, performs semantic search based on a user query, and generates answers grounded in the retrieved content.

---

## 🚀 Features

* Load plain text documents for embedding
* Split text into manageable chunks
* Generate and store vector embeddings using OpenAI
* Retrieve semantically similar documents using similarity search or score threshold
* Use LangChain's `RunnablePassthrough` for chaining query and retriever
* Final answer generation using `ChatOpenAI` with context-aware prompts

---

## 🧺 Technologies Used

| Category        | Tools / Libraries                         |
| --------------- | ----------------------------------------- |
| Vector DB       | [Chroma](https://www.trychroma.com/)      |
| Embeddings      | `OpenAIEmbeddings` via `langchain_openai` |
| Language Model  | `ChatOpenAI`                              |
| Text Splitting  | `CharacterTextSplitter` from LangChain    |
| Prompting       | `ChatPromptTemplate`                      |
| Chaining        | `RunnablePassthrough`, `StrOutputParser`  |
| Document Loader | `TextLoader`                              |
| Language        | Python                                    |

---

## 🥪 How It Works

1. Load a plain text file using `TextLoader`.
2. Split the text into chunks with overlap using `CharacterTextSplitter`.
3. Generate vector embeddings for the chunks with `OpenAIEmbeddings()`.
4. Store the chunks in Chroma vector database.
5. Perform a similarity search or a threshold-based search on a user query.
6. Pass retrieved documents + question through a prompt template to generate an answer.

---

## 🧠 Sample Prompt Template

```text
Answer the question based only on the following context:
{context}

Question: {question}
```

---

## ✅ Output Example

**User Query:**

> What is the text embedding and how does langchain help in doing it?

**Output:**

> (Generated answer from `ChatOpenAI` grounded on retrieved chunks.)

---

## 📉 Challenges Faced

* Understanding correct usage of `RunnablePassthrough()` to map query directly
* Handling `search_kwargs` properly as a dictionary (not tuple)
* Ensuring text chunks are properly formatted for embedding and retrieval
* Selecting an appropriate `score_threshold` for filtering noisy results
* Avoiding `KeyError` by correctly setting up input dictionaries for LangChain chains




## ✨ Author

Shehan

