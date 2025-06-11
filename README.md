# **RAGAgent: An Internet-Augmented Conversational Research Assistant**

**RAGAgent** is a self-contained, intelligent assistant that performs **Retrieval-Augmented Generation (RAG)** by integrating real-time web search, semantic document retrieval, and tool-augmented reasoning — all powered by open-source technologies and running locally without reliance on proprietary APIs.

The system leverages **Mistral-7B-Instruct** for multi-turn dialogue, **Chroma** vector storage for semantic memory, and LangChain’s agentic framework to provide accurate, real-world answers to complex queries through autonomous reasoning.

---

## **Project Objectives**

- Perform live web search using DuckDuckGo to retrieve real-time, relevant URLs.
- Extract, clean, and chunk online content using web loaders and character-based splitting.
- Generate dense semantic embeddings from chunks using `MiniLM` and store them in a vector database.
- Create and register a custom tool to enable semantic search over vectorized content.
- Implement an agentic framework for contextual dialogue using memory and tool use.
- Simulate a local, privacy-friendly research assistant capable of dynamic, multi-turn conversations.

---

## **Key Capabilities**

### **Multi-Turn Conversational Assistant**
- Maintains dialogue history using `ConversationBufferMemory`
- Responds to complex queries while preserving context across turns

### **Live Web Search + Document Chunking**
- Utilizes `duckduckgo_search` for up-to-date source discovery
- Extracts webpage content via `WebBaseLoader`
- Splits text into manageable chunks using `RecursiveCharacterTextSplitter`

### **Semantic Retrieval via Embeddings**
- Converts text chunks to vector embeddings with `all-MiniLM-L6-v2`
- Persists the vectors in a local `Chroma` vector database for retrieval

### **Tool-Augmented Reasoning**
- Registers a custom retriever tool using LangChain's `Tool()` interface
- Enables the agent to search relevant chunks dynamically during inference

---

## **Core Components**

- **Language Model**: `mistralai/Mistral-7B-Instruct-v0.1` (loaded locally via `transformers`)
- **Search Engine**: `duckduckgo_search.DDGS` for retrieving URLs
- **Document Loader**: `WebBaseLoader` for content extraction
- **Chunking**: `RecursiveCharacterTextSplitter` for splitting text into semantically useful chunks
- **Embeddings**: `HuggingFaceEmbeddings` with `all-MiniLM-L6-v2`
- **Vectorstore**: `Chroma` database for semantic chunk retrieval
- **Agent**: `ConversationalReactDescription` agent with integrated tools and memory
- **Memory**: `ConversationBufferMemory` to retain past interactions
