# 5. Project Development Phase

## Implemented Features

- FastAPI app startup and static-file mounting.
- HTML form input and comic preview templates.
- JSON input model and `/generate-comic/json` endpoint.
- Gemini Flash outline generation, model fallback attempts, response parsing, and procedural outline fallback.
- Gemini Pro story script generation, model fallback attempts, response parsing, and procedural script fallback.
- Pollinations.ai illustration requests with retries and locally generated placeholder panels after failure.
- Panel layout assembly from outline, script, and illustration results.
- Multi-page PDF creation with a cover and panel content.
- Export confirmation and PDF download routes.

## Main Workflow

1. `POST /generate` or `POST /generate-comic/json` receives the user's creative options.
2. The route derives a comic title and requests a five-panel outline.
3. The route requests the script and generates one image per outline panel.
4. `build_comic_layout` aligns each panel's text and image.
5. The form workflow renders `comic_preview.html`; the JSON workflow returns layout data and the PDF path.
6. `save_pdf` writes the downloadable file into `static/exports/`.

## Source Map

- App and routes: `app/main.py`, `app/routes.py`
- AI text: `app/gemini_flash.py`, `app/gemini_pro.py`
- Images and layout: `app/image_generator.py`, `app/layout_builder.py`
- PDF export: `app/exporters.py`
- Views: `templates/index.html`, `templates/comic_preview.html`, `templates/export_success.html`
- Pipeline tests: `test_pipeline.py`
- Python packages: `requirements.txt`