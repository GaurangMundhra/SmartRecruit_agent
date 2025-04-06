# 🤖 AI-Powered Recruitment System

An intelligent end-to-end recruitment assistant that leverages NLP and AI to streamline candidate selection, shortlisting, and interview scheduling.

---

## 🚀 Features

### 🧠 JD Summarizer Agent
- Extracts key **skills**, **responsibilities**, and **job roles** from job descriptions using NLP (e.g., spaCy).
- Outputs a structured summary to aid in candidate matching.

### 📄 CV Parser Agent
- Parses resumes (PDF/DOCX) and converts them into structured **JSON** data.
- Extracts name, email, skills, experience, education, and projects.

### 🔍 Matching Agent
- Compares job descriptions and resumes using:
  - **TF-IDF vectorization**
  - **Cosine similarity**
- Generates a **match score** (0 to 100) for each candidate.

### ✅ Shortlisting Agent
- Filters candidates based on a configurable **match score threshold** (e.g., 70%).
- Stores shortlisted candidates in a **SQLite database**.

### 📅 Interview Scheduler Agent
- Sends interview invites via email to shortlisted candidates.
- Logs all scheduling information and interactions into **SQLite** for memory and analytics.

---

## 🗂️ Project Structure


---

## 🛠️ Tech Stack

- **Python 3.8+**
- **spaCy** – NLP for JD and CV parsing
- **Scikit-learn** – TF-IDF & similarity scoring
- **SQLite3** – Lightweight database
- **smtplib / email** – Email scheduler
- **PyPDF2 / python-docx** – Resume text extraction

---

## ⚙️ How It Works

1. Upload Job Description → JD Summarizer extracts key terms.
2. Upload Resumes → CV Parser converts them to structured data.
3. Matching Agent calculates similarity scores for each candidate.
4. Shortlisting Agent filters candidates based on a score threshold.
5. Interview Scheduler emails shortlisted candidates and logs to SQLite.

---

## 💾 Database Schema

**Table: `candidates`**
| id | name | email | match_score | status | scheduled_date |

**Table: `logs`**
| id | action | timestamp | metadata |

---

## ✅ Installation

```bash
git clone https://github.com/yourusername/recruitment_ai.git
cd recruitment_ai
pip install -r requirements.txt
