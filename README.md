# Resume & Job Matching Assistant

A beginner-friendly Python web app that compares a resume with a job description. It extracts text from PDF/DOCX resumes, calculates a TF-IDF text-similarity score, highlights shared and potentially missing keywords, and lets users download a plain-text report.

> **Important:** The score is a text-similarity estimate, not a probability of getting hired and not a substitute for human judgment. Keyword suggestions should only be added to a resume when they truthfully describe the candidate's skills or experience.

## Features

- Upload a resume in PDF or DOCX format
- Paste a job description
- Calculate text similarity with TF-IDF and cosine similarity
- Display overlapping and potentially missing keywords
- Provide a resume-improvement checklist
- Download an analysis report
- No database or persistent resume storage in this demo

## Tech stack

- Python
- Streamlit
- scikit-learn
- pypdf
- python-docx

## Run locally

### 1. Install Python
Use Python 3.10 or newer.

### 2. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/resume-job-matching-assistant.git
cd resume-job-matching-assistant
```

### 3. Create and activate a virtual environment (recommended)

Windows:

```bash
python -m venv .venv
.venv\Scripts\activate
```

macOS/Linux:

```bash
python -m venv .venv
source .venv/bin/activate
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Start the app

```bash
streamlit run app.py
```

Streamlit will show a local URL, usually `http://localhost:8501`.

## Deploy online with Streamlit Community Cloud

1. Push this project to a GitHub repository.
2. Sign in to Streamlit Community Cloud.
3. Create a new app and select your repository.
4. Set the main file path to `app.py`.
5. Deploy.

The dependencies are listed in `requirements.txt`.

## Upload to GitHub using the website

1. Create a new repository named `resume-job-matching-assistant`.
2. Extract the ZIP file you downloaded.
3. Open the repository and choose **Add file → Upload files**.
4. Upload the project files and folders (not the ZIP itself).
5. Commit the files.

Alternatively, use Git from the project folder:

```bash
git init
git add .
git commit -m "Initial commit: Resume and Job Matching Assistant"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/resume-job-matching-assistant.git
git push -u origin main
```

Replace `YOUR-USERNAME` with your GitHub username.

## How the matching works

1. Text is extracted from the uploaded resume.
2. The app compares resume text and job-description text with TF-IDF features.
3. Cosine similarity is converted to a percentage for display.
4. A simple word-overlap scan lists shared terms and terms that may be worth reviewing.

This first version does not understand context perfectly, does not rank candidates, and may miss synonyms or skills expressed in different ways. A scanned PDF may not contain extractable text.

## Privacy and responsible use

- Do not upload documents without permission.
- This demo does not write uploaded resumes to a database or save them as files.
- When deployed, uploaded content is still processed by the hosting environment during the session. Review the host's policies before using real personal data.
- Do not use this tool as the sole basis for hiring or rejection decisions.
- Do not add a skill to a resume unless it accurately reflects the candidate.

## Project structure

```text
resume-job-matching-assistant/
├── app.py
├── requirements.txt
├── README.md
├── .gitignore
├── LICENSE
└── sample_job_description.txt
```

## Future improvements

- Add skill categories and synonym matching
- Support plain-text resumes
- Add downloadable PDF reports
- Add unit tests and CI
- Add optional OCR for scanned PDFs
- Add a clearer explanation of which parts of the job description match the resume
