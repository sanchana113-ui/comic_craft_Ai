# 6. Project Testing

## Existing Automated Coverage

`test_pipeline.py` contains integration tests for:

- Outline generation returning five structured panels.
- Story generation returning captions, narration, and dialogue.
- Image generation saving a PNG under `static/panels/`.
- Repeated image generation producing unique files.
- Layout construction aligning panel data and images.
- PDF creation and output-file existence.
- Homepage, image test route, JSON generation, export confirmation, PDF download, and form generation routes.

## How to Run

From the repository root, install the packages from `requirements.txt`, configure environment variables as needed, then run:

```powershell
python -m unittest test_pipeline.py
```

The suite is an integration suite, not a fully isolated unit suite. It may contact Gemini and Pollinations.ai, take time, and create PNG/PDF artifacts. Gemini has code-level fallbacks when the API key is absent or generation fails; image generation still makes external requests before it creates a local placeholder.

## Manual Checks

1. Start the app with `uvicorn app.main:app --reload`.
2. Open `http://127.0.0.1:8000/` and submit a prompt with each creative field filled in.
3. Confirm the preview contains five panels with text and images.
4. Download the PDF and confirm it opens and contains a cover plus panel pages.
5. Send a valid JSON request to `/generate-comic/json` and inspect the returned layout and PDF path.
6. Try image generation while the external service is unavailable and confirm the local placeholder path works.

## Reporting Results

Record the date, Python version, command, pass/fail result, and whether external services were available when running the suite. No test result is asserted by this document; execute the test command in the target environment to produce a current result.