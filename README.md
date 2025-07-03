# Semantic-Book-Recommender

# LiteraryLens: A Semantic Book Recommender

LiteraryLens is an intelligent book recommendation engine that helps you discover books based on their description, category, and emotional tone. Instead of relying on simple keyword matching, it uses semantic search to understand the *meaning* behind your query and suggests books that truly match the vibe you're looking for.

<img width="946" alt="image" src="https://github.com/user-attachments/assets/51a4aa8d-7b13-4a13-957f-9598e7ede097" />



---

## ✨ Features

-   **Semantic Search:** Enter a description, a theme, or a plot idea, and get recommendations that match the concept, not just the keywords.
-   **Emotional Tone Filtering:** Fine-tune your search by selecting a desired emotional tone, such as "Happy," "Suspenseful," or "Sad."
-   **Category Filtering:** Narrow down recommendations by genre, like "Fiction," "Science," or "History."
-   **Interactive UI:** A simple and clean user interface built with Gradio for easy interaction.
-   **Visual Recommendations:** Each recommended book is displayed with its cover, title, author, and a short description.

---

## 🛠️ Tech Stack & Architecture

This project combines modern data science and machine learning libraries to create a powerful recommendation pipeline:

-   **Backend:** Python
-   **Data Manipulation:** Pandas, NumPy
-   **UI Framework:** Gradio
-   **Natural Language Processing:**
    -   `langchain`: For orchestrating the NLP pipeline.
    -   `transformers` (HuggingFace): For accessing the open-source sentence-embedding model.
-   **Vector Database:**
    -   `chromadb`: To store and efficiently search through book description embeddings.
    -   `sentence-transformers`: Using the `all-MiniLM-L6-v2` model for generating high-quality vector embeddings.
-   **Dataset:** The book data was sourced from a Kaggle dataset.

### How It Works

The recommendation process follows these steps:
1.  **Data Loading & Preprocessing:** The book dataset from Kaggle is loaded, and book descriptions are prepared for processing.
2.  **Embedding Generation:** Each book description is converted into a numerical vector (an embedding) using a Sentence Transformer model. These embeddings capture the semantic meaning of the text.
3.  **Vector Storage:** The generated embeddings are stored in a ChromaDB vector database for fast similarity searches.
4.  **User Query:** A user enters a descriptive query, selects a category, and an emotional tone.
5.  **Semantic Search:** The user's query is converted into an embedding, which is then used to find the most similar book embeddings in ChromaDB.
6.  **Filtering & Ranking:** The initial list of semantically similar books is filtered by the selected category. If an emotional tone is chosen, the results are re-ranked based on the book's pre-calculated emotion scores.
7.  **Display Results:** The final recommendations are presented to the user through the Gradio interface.

---
## 🙏 Acknowledgements

-   This project utilizes a dataset of books from **Kaggle**.
-   The embedding models are provided by **HuggingFace** and the open-source community.
-   Built with the amazing **Gradio**, **LangChain**, and **ChromaDB** libraries.

