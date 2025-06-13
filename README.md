# TDS TA

## 🔗 Live Links

- 🚀 **API Endpoint**:   
- 📂 **GitHub Repository**: 
---

## 📌 Problem Statement

You are a student enrolled in the Tools in Data Science course. Out of kindness for the TAs, you've built an **API that auto-responds to student queries** based on:

-  TDS course content (as of 15 Apr 2025)  
-  Discourse posts from 1 Jan 2025 to 14 Apr 2025  

The goal is to answer student questions automatically by analyzing scraped data and provide relevant links from Discourse.

---


## 🗂️ Project Directory Structure & Run Instructions

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
├── project-tds-virtual-ta-q1.webp# Sample image for testing
├── requirements.txt              # Required Python libraries
├── test.yaml                     # Promptfoo test config
└── vercel.json                   # Vercel deployment config
