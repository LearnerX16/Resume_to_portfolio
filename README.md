# AI Resume Portfolio Generator

An interactive web application that transforms plain-text resumes into professional, multi-themed portfolio websites using Gemini AI.

## 🚀 Features

* Convert raw resume text into a structured portfolio
* Gemini-powered resume information extraction
* Four interactive portfolio themes:

  * Vivid
  * Bold
  * Editorial
  * Dark
* Live portfolio preview using an interactive iframe
* Automatic theme synchronization between the portfolio and preview interface
* Sample Portfolio mode using a pre-loaded `resume.txt`
* Fault-tolerant JSON extraction for incomplete or inconsistent AI responses
* Ephemeral sessions with no permanent portfolio storage

## 🏗️ Architecture

```text
                    ┌──────────────────────┐
                    │       User           │
                    │ Resume / Sample      │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Frontend Interface │
                    │   index.html + CSS   │
                    └──────────┬───────────┘
                               │
                         POST /api/generate
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Python Backend     │
                    │   api/generate.py    │
                    │                      │
                    │ • Gemini API call    │
                    │ • JSON extraction    │
                    │ • Validation         │
                    │ • HTML generation    │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │      Gemini AI       │
                    │  Resume → JSON Data  │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │  Portfolio Template  │
                    │ template.html        │
                    │ style.css            │
                    └──────────┬───────────┘
                               │
                               ▼
                    ┌──────────────────────┐
                    │   Live Preview       │
                    │      iframe          │
                    └──────────────────────┘
```

---

## 🛠️ Tech Stack

* **Frontend:** HTML, CSS, JavaScript
* **Backend:** Python
* **AI:** Gemini API
* **Deployment:** Vercel

---

## 📁 Project Structure

```text
Resume_to_portfolio/
│
├── api/
│   └── generate.py       # Serverless backend and Gemini integration
│
├── index.html            # Main application interface
├── launcher.css          # Generator UI styling
├── template.html         # Base portfolio template
├── style.css             # Portfolio theme styling
├── resume.txt            # Sample resume
├── requirements.txt      # Python dependencies
├── vercel.json            # Vercel configuration
└── .gitignore
```


## 💻 Local Setup

### 1. Clone the repository

```bash
git clone https://github.com/LearnerX16/Resume_to_portfolio.git
cd Resume_to_portfolio
```

### 2. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 3. Configure Gemini API Key

Create a `.env` file in the project root:

```text
GEMINI_API_KEY=your_gemini_api_key
```

Do **not** commit the `.env` file to GitHub.

The `.gitignore` file already excludes `.env`.

### 4. Run the application

```bash
python main.py
```
