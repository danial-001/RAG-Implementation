:

🧠 Legal RAG System (Retrieval-Augmented Generation)
📌 Project Overview
This project implements a Retrieval-Augmented Generation (RAG) pipeline designed to assist with legal document analysis. Given a user’s legal query, the system:

Retrieves relevant context from legal PDFs,

Generates legal-style answers using a language model.

The goal is to provide helpful legal answers using open-source tools and free APIs.

🔧 Technologies Used
Component	Tool/Library
Language Model	google/flan-t5-large (for answer generation)
Embedding Model	Google Gemini API (models/embedding-001)
Vector DB	FAISS for similarity search
PDF Parsing	PyMuPDF (fitz)
Platform	Google Colab (Python Notebook)

📁 Data Processing Flow
Load Legal PDFs from Google Drive (limit 50).

Extract Text using PyMuPDF.

Chunk Text into 500-word segments.

Generate Embeddings for each chunk using Gemini's embedding API.

Store in FAISS for fast similarity-based retrieval.

On query, embed the question and retrieve top 5 similar chunks.

Generate an answer using FLAN-T5 based on the retrieved context.

🧪 Sample Queries
📄 Query 1:
Question: "Why was the Nawaz case dismissed?"

Answer:

The court dismissed the Nawaz case because the plaintiffs filed the action after the limitation period had expired. Additionally, the court found no negligence or breach of legal duty by the defendants and determined that the plaintiffs had not suffered damages due to their representation.

📄 Query 2:
Question: "What was the judgment in the Galaxy vs Chelliah case?"

Answer:

Mr. Chelliah was awarded $288,577.10 in damages, including HST, against Galaxy. Galaxy was also ordered to pay $45,282.27 in legal costs. The judgment included pre-judgment interest and was based on proven contractual breaches.

💡 Why FLAN-T5?
Due to API budget constraints, we used google/flan-t5-large for generation instead of paid models like ChatGPT or Gemini Pro. FLAN-T5 is open-source and suitable for prototyping, though not as powerful as proprietary models.

📌 Limitations & Future Improvements
FLAN-T5 can be replaced by more advanced models (e.g., Gemini Pro or Claude) for better generation quality.

A frontend UI can be added for easier interaction.

Document ingestion can be made dynamic via file upload.

