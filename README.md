# royalty-qna
Interactive Q&amp;A tool for mining royalty contracts using GPT-4o and Chroma. Upload a PDF, extract and embed text, and ask precise legal-style questions in natural language. Built for fast retrieval, deterministic answers (temperature 0), and easy local or Colab use.

# Mining Royalty Q&A Tool

Ask precise, legal-style questions about mining royalty contracts using `GPT-4o` and `Chroma` for context-aware retrieval.

> Upload your contract PDF → Embed and chunk text → Ask questions → Get answers sourced from the document.

---

## Features

-  PDF text extraction (via `PyPDF2`)
-  Embedding + retrieval using `ChromaDB` and `text-embedding-3-small`
-  Accurate answers from `GPT-4o` (with temperature=0)
-  Interactive Q&A loop in **Colab** or locally
-  Table-aware prompt formatting for structured data
-  Debug context visibility to improve retrieval accuracy

---


## How to Use (Colab)

1. Open the [Colab Notebook](https://colab.research.google.com/drive/1rSVEHGrbKSXVE4CX8uGx5U5M2TqXp1ZQ?usp=sharing)
2. Run each cell:
   - Install dependencies
   - Upload your PDF
   - Enter your OpenAI API key
3. Ask questions in plain English (e.g., _"What is the NSR on the Property?"_)

---

## Tech Stack

| Tool         | Purpose                     |
|--------------|-----------------------------|
| `OpenAI GPT-4o` | Natural language answers      |
| `text-embedding-3-small` | Embedding PDF chunks         |
| `ChromaDB`    | Local vector search engine   |
| `PyPDF2`      | PDF text extraction          |
| `tiktoken`    | Token-aware chunking         |

---

## Directory Structure
| File |
|------------------------------------------|
| royalty_qna.ipynb # Colab-ready notebook |
| README.md # This file |
| example_contract.pdf # (Optional sample contract) |


---

## Notes & Tips

- Works best on **text-based PDFs**, not scanned images (OCR support can be added).
- For best accuracy, the tool quotes sources and uses top-`k` retrieval with context auditing.
- Chunking is optimized for ~500 tokens per segment for balance between recall and cost.

---

## API Key Handling

We use `getpass.getpass()` in Colab to avoid storing or exposing your OpenAI API key. You can also load it via environment variables for local use.

---

## Next Steps

- [ ] Add OCR support (for scanned PDFs)
- [ ] Add Streamlit or Flask UI for local deployment
- [ ] Save and re-load embedded Chroma collections
- [ ] Support multi-PDF contract indexing

---

## License

MIT License (see `LICENSE.md`)

---



