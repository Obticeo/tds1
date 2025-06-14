# RAG-Based Virtual Teaching Assistant

A Retrieval Augmented Generation (RAG) system that provides automated responses to student queries using course content and forum discussions.

## 🚀 Architecture Overview

The system consists of three main components:

1. **Content Scrapers**
   - [`contentscrapper.py`](contentscrapper.py): Scrapes course documentation using Playwright
   - [`discoursescrapper.py`](discoursescrapper.py): Extracts forum discussions from Discourse

2. **Knowledge Base**
   - Uses SQLite database ([`knowledge_base.db`](knowledge_base.db)) with two tables:
     - `discourse_chunks`: Stores forum post segments
     - `markdown_chunks`: Stores course documentation chunks
   - Each chunk stores embeddings for semantic search

3. **Query Engine** ([`app.py`](app.py))
   - FastAPI-based REST API
   - Processes both text and image queries
   - Uses vector similarity to find relevant content
   - Generates contextual responses using LLM

## 💡 How It Works

1. **Content Ingestion**
   - Course content and forum posts are scraped
   - Text is chunked and converted to embeddings
   - Stored in SQLite with metadata and source URLs

2. **Query Processing**
   ```mermaid
   graph LR
   A[User Query] --> B[Generate Embedding]
   B --> C[Find Similar Content]
   C --> D[Enrich with Context]
   D --> E[Generate Answer]
   E --> F[Parse Response]
   ```

3. **Response Generation**
   - Finds relevant content using cosine similarity
   - Enriches results with adjacent text chunks
   - Uses LLM to generate natural responses
   - Includes source URLs for verification

## 🛠️ Key Features

- Multimodal support (text + images)
- Context-aware responses
- Source attribution
- Adaptive & Dynamic similarity thresholds
- Error resilience and fallbacks
- Health monitoring

## 📋 API Endpoints

```text
POST /query
- Accepts question and optional image
- Returns answer with source links

```

## 🔧 Configuration

Key environment variables:
- `API_KEY`: LLM API authentication
- `DB_PATH`: SQLite database location (default: "knowledge_base.db")
- `SIMILARITY_THRESHOLD`: Matching threshold (default: 0.6)

## 🚀 Getting Started

1. Install dependencies:
```sh
pip install -r requirements.txt
```

2. Set up environment:
```sh
# Add your API key
```

3. Run the application:
```sh
python app.py
```

## 📝 License

[MIT License](LICENSE)

## 🗂️ Project Directory Structure

```bash
tds1/
├── .gitignore                    # Files to ignore in Git
├── LICENSE                       # MIT License
├── README.md                     # Project documentation
├── app.py                        # FastAPI app logic
├── asgi.py                       # ASGI entry point for Vercel
├── contentscrapper.py            # Scraper for TDS course content
├── discoursescrapper.py          # Scraper for Discourse posts
├── knowledge_base.db             # SQLite DB of scraped content
├── metadata.json                 # Metadata for scraped items
├── requirements.txt              # Required Python libraries
└── vercel.json                   # Vercel deployment config
