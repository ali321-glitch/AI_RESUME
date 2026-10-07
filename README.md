
# 📄 ATS Resume Analyzer

A Streamlit app that scores your resume for Applicant Tracking Systems (ATS) and suggests concrete improvements, powered by Google Gemini Flash.

## Features
- Upload a resume as **PDF, DOCX or TXT**
- Optional **job description** for keyword matching
- ATS score (0-100) with a breakdown: keywords, formatting, content, impact, readability
- Strengths, weaknesses and **missing keywords**
- Prioritized improvement suggestions and example bullet rewrites
- Download the report as JSON

## Run locally
```bash
git clone https://github.com/<your-username>/<your-repo>.git
cd <your-repo>
python -m venv venv
source venv/bin/activate        # Windows: venv\Scripts\activate
pip install -r requirements.txt
```

Get a free API key from [Google AI Studio](https://aistudio.google.com/apikey), then either:

- paste it in the app sidebar, or
- set an environment variable: `export GEMINI_API_KEY="your-key"` (Windows: `set GEMINI_API_KEY=your-key`), or
- create `.streamlit/secrets.toml` containing `GEMINI_API_KEY = "your-key"`

```bash
streamlit run app.py
```

## Deploy on Streamlit Community Cloud
1. Push this repo to GitHub.
2. Go to [share.streamlit.io](https://share.streamlit.io) and click **Create app**.
3. Select your repo, branch `main`, main file `app.py`.
4. Open **Advanced settings → Secrets** and add: `GEMINI_API_KEY = "your-key"`
5. Click **Deploy**.

## Configuration
The model defaults to `gemini-2.5-flash`. You can change it in the sidebar to any Gemini Flash model your key can access.

## Notes
- Scanned/image-only PDFs have no extractable text, which also means real ATS systems cannot read them.
- The score is an AI estimate, not the output of any specific commercial ATS.
- Never commit your API key. Keep `.streamlit/secrets.toml` out of git.
