#  FranchiseOps RAG Builder – Milestone 3

## Project Overview

FranchiseOps RAG Builder is an AI-powered Question Answering System built using the **Retrieval-Augmented Generation (RAG)** architecture. The application enables users to ask questions from a collection of franchise-related documents, and it retrieves the most relevant information before generating accurate, context-aware responses using a Large Language Model (LLM).

This milestone combines the work completed in **Milestone 1** and **Milestone 2**, while introducing an expanded knowledge base, extensive testing, and improved project documentation.

---

# Milestone 3 Objectives

* ✅ Merge **Milestone 1** and **Milestone 2** into a single notebook.
* ✅ Develop a dedicated notebook for the complete RAG Pipeline.
* ✅ Expand the document knowledge base with significantly more PDFs.
* ✅ Validate the RAG system using **30+ different user queries**.
* ✅ Update the GitHub repository with proper documentation and team contributions.

---

# Project Structure

```
FranchiseOps-RAG-Builder/
│
├── Combined_Milestone.ipynb          # Milestone 1 + Milestone 2
├── FranchiseOps_RAG_Builder.ipynb    # Complete RAG Pipeline
│
├── data/
│   ├── PDF_1.pdf
│   ├── PDF_2.pdf
│   ├── PDF_3.pdf
│   ├── ...
│
├── vector_store/
│
├── screenshots/
│
├── README.md
│
└── requirements.txt
```

---

# System Architecture

```
                  User Query
                       │
                       ▼
                Query Processing
                       │
                       ▼
          Embedding Generation
                       │
                       ▼
              Vector Database Search
                       │
             Retrieve Relevant Chunks
                       │
                       ▼
     Retrieved Context + User Question
                       │
                       ▼
             Large Language Model
                       │
                       ▼
               Generated Response
```

---

#  Technologies Used

* Python
* Jupyter Notebook
* LangChain
* FAISS (Vector Database)
* HuggingFace Embeddings
* Google Gemini / OpenAI LLM
* PyPDF
* Recursive Character Text Splitter
* dotenv
* Streamlit (if applicable)

---

#  Knowledge Base

The knowledge base has been significantly expanded compared to previous milestones.

### Improvements

* Added multiple new PDF documents.
* Increased document diversity.
* Improved retrieval accuracy.
* Enhanced context coverage.
* Better semantic search performance.

---

#  RAG Pipeline

The implemented Retrieval-Augmented Generation workflow consists of:

1. Loading PDF documents
2. Extracting document text
3. Splitting text into chunks
4. Creating embeddings
5. Storing embeddings in a vector database
6. Retrieving relevant document chunks
7. Sending retrieved context to the LLM
8. Generating an accurate response

---

#  Testing

The RAG application was evaluated using **30+ different queries** to validate its robustness.

The testing covered:

* Simple factual questions
* Multi-document queries
* Context-based questions
* Long queries
* Ambiguous questions
* Information retrieval accuracy
* Edge cases
* Unknown questions
* Response consistency

### Outcome

* Successfully retrieved relevant document chunks.
* Generated context-aware responses.
* Demonstrated stable performance across diverse query types.

---

#  How to Run

### Clone Repository

```bash
git clone <repository-url>
```

### Install Dependencies

```bash
pip install -r requirements.txt
```

### Add Environment Variables

Create a `.env` file.

Example:

```text
GOOGLE_API_KEY=YOUR_API_KEY
```

(or your respective LLM API key)

### Run the Notebook

Open Jupyter Notebook and execute:

* `Combined_Milestone.ipynb`
* `FranchiseOps_RAG_Builder.ipynb`

---

# Features

* PDF Question Answering
* Retrieval-Augmented Generation (RAG)
* Semantic Search
* Vector Similarity Search
* Context-Aware Responses
* Multi-document Support
* Expanded Knowledge Base
* Robust Query Testing

---

# Team Contributions

| Team Member | Contribution                                                       |
| ----------- | ------------------------------------------------------------------ |
| Tazreen Rahman    | Milestone 1 development, authentication, UI integration            |
| Boddu Mounika     | Milestone 2 implementation, embeddings, vector database            |
| Akeera Nandan, Divya Sree Koneti, Gillala Sai Gouthami   | RAG pipeline, testing (30+ queries), documentation, GitHub updates |
| All Members | Code review, debugging, integration, final submission              |


---

#  Milestone Deliverables

### ✅ Deliverable 1

Combined notebook containing:

* Milestone 1
* Milestone 2

### ✅ Deliverable 2

Dedicated notebook containing:

* Complete RAG Pipeline

### ✅ Deliverable 3

Expanded PDF dataset

### ✅ Deliverable 4

30+ successful evaluation queries

### ✅ Deliverable 5

Updated GitHub repository with documentation

---

# 📖 Future Enhancements

* Hybrid Search (Keyword + Semantic Search)
* Chat History Memory
* Multi-modal document support
* Real-time document uploads
* Improved retrieval ranking
* Citation-based answers
* Web interface deployment
* Performance optimization

---

# Conclusion

Milestone 3 successfully integrates the work completed in previous milestones into a unified solution while introducing a scalable Retrieval-Augmented Generation (RAG) pipeline. The expanded knowledge base, extensive testing with over 30 queries, and updated project documentation demonstrate the system's ability to provide reliable, context-aware answers from multiple documents.

