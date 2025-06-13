# 🧑‍🏫 TDS Virtual TA – Automated Teaching Assistant

An AI-powered Teaching Assistant for the **Tools in Data Science (TDS)** course (Jan 2025 batch) of **IIT Madras' Online BSc Degree in Data Science**.  
This assistant helps answer student queries using scraped course content and Discourse discussions.

---

## 🔗 Live Links

- 🚀 **API Endpoint**: [https://tds-project-1-virtual-ta-two.vercel.app/query](https://tds-project-1-virtual-ta-two.vercel.app/query)  
- 📂 **GitHub Repository**: [shivam91264/TDS-PROJECT-1-VIRTUAL-TA](https://github.com/shivam91264/TDS-PROJECT-1-VIRTUAL-TA)

---

## 📌 Problem Statement

You are a student enrolled in the Tools in Data Science course. Out of kindness for the TAs, you've built an **API that auto-responds to student queries** based on:

- 📘 TDS course content (as of 15 Apr 2025)  
- 💬 Discourse posts from 1 Jan 2025 to 14 Apr 2025  

The goal is to answer student questions automatically by analyzing scraped data and provide relevant links from Discourse.

---

## ✅ Features

- FastAPI-based POST API at `/query`  
- Accepts plain text questions and optional base64‑encoded images  
- Searches relevant answers from a SQLite knowledge base  
- Returns:
  - An `answer` string  
  - A `links` array of related Discourse posts  
- Compatible with [Promptfoo](https://github.com/promptfoo/promptfoo) for evaluation  
- Deployed on Vercel 

---

## 🗂️ Project Directory Structure & Run Instructions

```bash
TDS-PROJECT-1-VIRTUAL-TA/
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

## 🧪 Test & Evaluation

Test the project using the provided `test.yaml`

Test.yaml testing command :-- npx promptfoo eval -c test.yaml --no-cache

