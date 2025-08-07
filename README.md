# 🧠 Legal Document Q&A System (RAG-based) – FLAN-T5 Implementation

This project is a Retrieval-Augmented Generation (RAG) system designed to answer legal questions from court judgments in PDF format. Using Google’s `FLAN-T5` for answer generation and Gemini Embeddings + FAISS for document retrieval, it enables users to ask natural language queries and get legal summaries based on actual legal documents.

---

## 🔧 Technologies Used

- 🧾 **PDF Parsing**: `PyMuPDF` (`fitz`)
- 🧠 **Embeddings**: Google `Gemini` model (`embedding-001`)
- 📚 **Similarity Search**: `FAISS` (L2 Index)
- 🤖 **Answer Generation**: `google/flan-t5-large` from HuggingFace
- 📓 **Platform**: Google Colab (Single Notebook)

---

## ⚙️ How it Works

1. **PDF Ingestion**: Loads up to 50 court PDF files from Google Drive.
2. **Chunking**: Breaks each document into ~500-word chunks.
3. **Embedding**: Generates vector embeddings for each chunk using Gemini's `embedding-001`.
4. **Indexing**: Stores all vectors in a FAISS index using L2 (Euclidean) distance.
5. **Querying**: Converts the user’s legal query to a vector and retrieves top 5 most relevant chunks.
6. **Answer Generation**: Constructs a prompt and feeds it to `FLAN-T5` to generate a legal-style summary answer.

---

## 🧪 Example Queries and Answers

### **Query 1:**
**Q:** What were the legal findings in the construction dispute between Galaxy Communities and Chelliah?

**A:**  
The Court of Justice of Ontario found that Mr. Chelliah had proven damages of $288,577.10, including HST, and is entitled to judgment against Galaxy for the same amount, plus pre-judgment interest pursuant to the Courts of Justice Act, RSO 1990, c.

---

### **Query 2:**
**Q:** Why was the Nawaz case dismissed?

**A:**  
The Defendants moved under Rule 20 of the Rules of Civil Procedure for an Order dismissing the action. The claim involved solicitor’s negligence against Keith Juriansz and damages against Vault Capital Inc. and 2439857 Ontario Inc., their former mortgagee.

---

## ✅ Project Highlights

- ✔️ Uses **open-source/free tools** (FLAN-T5, Gemini, FAISS) – no API costs.
- ✔️ Handles unstructured PDF documents and makes them searchable.
- ✔️ Answers are **context-aware**, derived directly from court documents.
- ✔️ Fully self-contained in **a single Google Colab notebook**.

---

## 📁 Project Structure

This project does not use folders. It’s built in a single Google Colab notebook for simplicity. All operations from loading PDFs to answer generation are handled in sequence.

---

## ❓ Why FLAN-T5?

FLAN-T5 is used for answer generation due to:
- Free availability
- No need for API keys
- Works well for structured question answering

⚠️ **Note**: While FLAN-T5 is effective for prototyping, performance may be lower than commercial models like Gemini Pro or ChatGPT.

---

## 📌 Next Steps / Improvements

- Add citation mapping to chunks for verifiability.
- Use paid models (e.g., Gemini Pro) for production-grade accuracy.
- Build a lightweight web UI using Gradio or Streamlit.

---

## 🗃️ Assignment Objective

This implementation fulfills the task from **Jinnah Tech’s ML Expert assignment**:
> *"Build a system to generate legal answers from PDFs using retrieval and generation."*

---

## 📤 How to Run

Upload your court PDFs to Google Drive → Set your `pdf_folder` path → Run all cells in the notebook.

---

## 📄 License

This project is built for educational & evaluation purposes.
