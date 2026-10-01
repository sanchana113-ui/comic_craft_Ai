# 7. Project Documentation

## Prerequisites

- Python installed and available as `python` in a terminal.
- Dependencies from `requirements.txt`.
- Internet access for remote Gemini and Pollinations.ai generation.
- A Gemini API key for Gemini-backed text generation. Text fallback content is used when the key is missing or the service fails.
- `POLLINATIONS_TOKEN` is optional; the image service also works anonymously subject to its service limits.

## Local Setup

From the repository root in PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install -r requirements.txt
```

Set `GEMINI_API_KEY` in a local `.env` file or in the process environment. Do not commit `.env`; use `.env.example` as a reference and keep real credentials private. The current image integration reads the optional `POLLINATIONS_TOKEN` environment variable.

## Run the Application

```powershell
uvicorn app.main:app --reload
```

Open `http://127.0.0.1:8000/` in a browser. The app creates `static/panels/` and `static/exports/` as needed.

## Main Routes

- `GET /`: comic prompt form.
- `POST /generate`: form submission and HTML preview.
- `POST /generate-comic/json`: JSON generation API.
- `GET /test-image`: direct image-generation utility.
- `GET /download-pdf?pdf_path=...`: download an exported PDF.
- `GET /export-success`: export confirmation page.

## Configuration Note

The current illustration code in `app/image_generator.py` uses Pollinations.ai, not a Hugging Face Stable Diffusion endpoint. The text modules use Gemini when configured. Keep this distinction current if integrations change.