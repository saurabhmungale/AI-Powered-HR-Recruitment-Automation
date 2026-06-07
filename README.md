# AI-Powered HR Recruitment Automation System

An end-to-end AI recruitment automation system that automatically collects resumes from Google Drive, extracts candidate information using LLM, filters qualified candidates, and sends interview invitation emails using n8n workflows.

---

## 🎯 Problem Statement

HR departments in MNCs receive thousands of resumes for senior positions. Manually reviewing each resume is time-consuming, inefficient, and prone to human error. This system automates the entire recruitment pipeline.

---

## 🏗️ System Architecture

```
Resumes (Google Drive)
        ↓
Python Pipeline (Google Colab)
        ↓
PDF/DOCX Text Extraction (PyMuPDF)
        ↓
Groq LLM Parsing (LLaMA 3.1)
        ↓
Qualification Filtering
        ↓
Excel Export → Google Sheets
        ↓
n8n Workflow Automation
        ↓
Gmail Interview Invitations ✅
```

---

## ⚙️ Tech Stack

| Component | Technology |
|---|---|
| Language | Python 3.12 |
| LLM | Groq API (LLaMA 3.1-8b-instant) |
| PDF Extraction | PyMuPDF (fitz) |
| DOCX Extraction | python-docx |
| Cloud Storage | Google Drive API |
| Data Export | Pandas, OpenPyXL |
| Workflow Automation | n8n |
| Email | Gmail (OAuth2) |
| Notebook | Google Colab |

---

## 🚀 Features

- ✅ Automatically downloads resumes from Google Drive
- ✅ Extracts text from PDF and DOCX files
- ✅ Parses candidate info using Groq LLM
- ✅ Extracts name, email, phone, experience, skills
- ✅ Filters candidates based on experience and skills
- ✅ Exports structured data to Excel/Google Sheets
- ✅ n8n workflow detects new candidates automatically
- ✅ Sends personalized interview invitation emails via Gmail

---

## 📋 Extracted Candidate Fields

- Candidate Name
- Email & Phone
- Total Experience Years
- Core AI Skills (ML, Deep Learning, NLP, GenAI, LLMs, RAG, PyTorch, LangChain)
- Cloud & MLOps Skills (AWS, Azure, GCP, Docker, Kubernetes, MLflow, FastAPI)
- Architecture & Leadership Skills
- Qualification Status (YES/NO)

---

## 🔧 Installation & Setup

### 1. Clone the repository
```bash
git clone https://github.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation.git
```

### 2. Install dependencies
```bash
pip install groq pymupdf python-docx pandas openpyxl google-api-python-client google-auth
```

### 3. Configure credentials
- Add your `Groq API Key` in the notebook
- Add your `Google Service Account JSON` file
- Set your `Google Drive Folder ID`

### 4. Run the notebook
- Open `Resume parsing.ipynb` in Google Colab
- Run all cells sequentially

### 5. Setup n8n workflow
- Connect Google Sheets Trigger
- Add IF node for qualification filter
- Connect Gmail node for email automation

---

## 📊 Qualification Criteria

Candidates are marked `is_qualified: YES` if they meet:
- Minimum **3+ years** of experience
- At least **1 matching AI or MLOps skill**

---

## 🔄 n8n Workflow

```
Google Sheets Trigger
        ↓
IF node (is_qualified == YES)
        ↓
Gmail → Send Interview Invitation
```

---

## 📁 Project Structure

```
AI-Powered-HR-Recruitment-Automation/
│
├── Resume parsing.ipynb       # Main pipeline notebook
├── output/
│   └── resume_data.xlsx       # Generated candidate data
├── downloaded_resumes/        # Downloaded PDF/DOCX files
└── README.md
```
## 📸 Screenshots

### Excel Output
![Excel](https://raw.githubusercontent.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation/main/images/excel_output.png)

### n8n Workflow
![n8n](https://raw.githubusercontent.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation/main/images/n8n_workflow.jpg)

### Email Sent
![Email](https://raw.githubusercontent.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation/main/images/email_sent.jpg)

### Email Inbox
![Email Inbox](https://raw.githubusercontent.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation/main/images/email_inbox.jpg)

### Pipeline Output
![Pipeline](https://raw.githubusercontent.com/saurabhmungale/AI-Powered-HR-Recruitment-Automation/main/images/pipeline_output.jpg)
---

## 🛠️ Built With

- [Groq](https://groq.com/) - LLM API
- [n8n](https://n8n.io/) - Workflow Automation
- [Google Drive API](https://developers.google.com/drive) - Cloud Storage
- [PyMuPDF](https://pymupdf.readthedocs.io/) - PDF Extraction

---

## 👨‍💻 Author

**Saurabh Mungale**
Data Science with Generative AI | PW Skills
[GitHub](https://github.com/saurabhmungale) | [LinkedIn](#) | [Kaggle](#)
