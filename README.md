# 🎥 Multimodal Video RAG (Retrieval-Augmented Generation)

An end-to-end Multimodal Video Retrieval-Augmented Generation (RAG) pipeline that allows users to seamlessly chat with and query video content. By combining advanced frame-based embedding techniques, vector indexing, and state-of-the-art vision-language models, this system turns video files into searchable, conversational knowledge bases.

---

## 🚀 Key Features
* **Multimodal Indexing:** Cross-references temporal video frames and textual transcripts together inside a unified vector space.
* **Vector Architecture via LanceDB:** Utilizes LanceDB for high-performance serverless storage of both multi-modal image/text embeddings.
* **Vision-Language Synthesis:** Leverages OpenAI's `gpt-4-vision-preview` to answer highly complex contextual questions about visual events, on-screen text, and continuous video timelines.
* **Orchestration Framework:** Powered by LlamaIndex for seamless document data management and retrieval pipelines.

---

## 🛠️ Pipeline Architecture

The system converts a standard video clip into a chat-ready asset through a multi-stage pipeline:

1. **Video Parsing:** The ingestion script samples frames at a specified frame rate (FPS) and extracts audio transcripts if available.
2. **Embedding Generation:** Visual frames and descriptive metadata are vectorized into continuous embedding spaces using multimodal models (e.g., CLIP).
3. **Vector Vectorization & Indexing:** LanceDB indexes the multimodal data arrays, facilitating super-fast top-$k$ visual similarity lookups.
4. **Context Retrieval:** When a user poses a question (e.g., *"What color jacket was the person wearing at the timestamp where the car appears?"*), the pipeline fetches the contextually closest video frames.
5. **Synthesis:** The retrieved images along with the text prompt are fed into `gpt-4-vision-preview` to generate a accurate, grounded response.

---
