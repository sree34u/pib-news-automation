# 📰 PIB News Automation & Summarization Pipeline

![Python](https://img.shields.io/badge/Python-3.10%2B-blue)
![Playwright](https://img.shields.io/badge/Playwright-Automation-green)
![CI](https://img.shields.io/badge/GitHub%20Actions-CI%2FCD-brightgreen)
![LLM](https://img.shields.io/badge/LLM-Local%20GPT4All-orange)
![License](https://img.shields.io/badge/License-MIT-lightgrey)

**End-to-end Data QA automation pipeline** showcasing browser automation, data validation, AI-assisted summarization, and CI/CD execution with production-grade structure.

---

## 🚀 Project Overview

This project automatically:

1. Scrapes the latest **Press Information Bureau (PIB)** news releases  
2. Extracts and cleans full article content  
3. Summarizes each article into **3 concise, factual bullet points** using a **local LLM (offline & free)**  
4. Saves outputs as structured JSON files  
5. Executes end-to-end via **GitHub Actions**, producing downloadable artifacts  

Designed to reflect **real-world QA Automation / SDET practices**, not just scripting.

---

## 🧠 Key Skills Demonstrated

- ✅ Browser automation using **Playwright (Python)**
- ✅ Stable scraping with explicit selectors and waits
- ✅ Data validation and content cleaning
- ✅ AI-assisted summarization using **local LLM (GPT4All)**
- ✅ Clean architecture & separation of concerns
- ✅ Virtual environment isolation
- ✅ CI/CD automation using **GitHub Actions**
- ✅ Artifact-based verification for CI outputs

---

## 📁 Project Structure

<pre> 
pib-news-automation/
├── README.md
├── requirements.txt
├── main.py
├── scraper/
│   └── scrape_pib.py
├── processor/
│   ├── clean_articles.py
│   └── summarize_articles.py
├── data/
│   ├── raw/
│   │   └── pib_news.json
│   └── processed/
│       ├── cleaned_news.json
│       └── summarized_news.json
└── .github/
    └── workflows/
        └── run_pipeline.yml
 </pre>
---

## ⚙️ Technology Stack

| Category | Tools |
|-------|------|
| Language | Python 3.x |
| Automation | Playwright (Python) |
| Parsing | BeautifulSoup |
| HTTP | Requests |
| LLM | GPT4All (local, offline) |
| CI/CD | GitHub Actions |
| Output | JSON artifacts |

---

## 🕷️ Data Pipeline Flow

<div align="center">

<b>PIB Website</b><br>
⬇️<br>
<b>Playwright Scraper</b><br>
⬇️<br>
<b>Raw JSON (titles + links)</b><br>
⬇️<br>
<b>Content Extraction & Cleaning</b><br>
⬇️<br>
<b>Cleaned JSON</b><br>
⬇️<br>
<b>Local LLM Summarization</b><br>
⬇️<br>
<b>Summarized JSON (final artifact)</b>

</div>


---

## 🧪 Testing Strategy

While this project focuses on automation pipelines rather than traditional UI test cases, core testing principles are applied:

- Validation of scraped data (non-empty titles, valid URLs)
- Schema consistency across pipeline stages
- Deterministic outputs for CI verification
- Failure isolation between scraping, processing, and summarization

---

## 🖥️ Run Locally
 
1️⃣ Clone Repository
```python
git clone https://github.com/sree34u/pib-news-automation.git
cd pib-news-automation
```
2️⃣ Create & Activate Virtual Environment
```python
python3 -m venv .venv
source .venv/bin/activate
```
3️⃣ Install Dependencies
```python
pip install -r requirements.txt
playwright install
```
4️⃣ Run Full Pipeline
```python
python main.py
```
---
## 🤖 GitHub Actions (CI/CD)
### Workflow Behavior
1. Installs Python 3.11
2. Installs Playwright and OS dependencies
3. Executes full scraping → cleaning → summarization pipeline
4. Uploads final summarized JSON as a build artifact

---
### How to Run
1. Navigate to Actions tab
2. Select Run PIB News Automation
3. Click Run workflow
4. Download summarized_news.json from artifacts

---
## 📦 Output Files

| File	| Description |
|-------|------|
data/raw/pib_news.json	|Raw scraped titles & links
data/processed/cleaned_news.json	|Cleaned article content
data/processed/summarized_news.json	|Final summarized output

---
## ⚙️ CI Reliability Considerations
- Headless browser execution optimized for GitHub Actions
- Scraping limited to first 10 articles to reduce flakiness
- Explicit selectors to minimize false positives
- Fully reproducible CI environment from scratch

---
## 📜 License
MIT License