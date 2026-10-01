# 3. Project Design Phase

## Architecture

```text
Browser form / JSON client
          |
          v
     FastAPI routes
          |
          +--> Gemini Flash outline (procedural fallback)
          +--> Gemini Pro script (procedural fallback)
          +--> Pollinations.ai panel art (local placeholder fallback)
          |
          v
    Comic layout builder
       /           \
 HTML preview    PDF exporter
                   |
                   v
        static/exports/*.pdf
```

## Main Components

- `app/main.py` creates the FastAPI application, ensures static output directories exist, and mounts static assets.
- `app/routes.py` validates JSON input and coordinates the form, JSON, test-image, preview, and PDF-download workflows.
- `app/gemini_flash.py` creates the five-panel outline and a procedural fallback.
- `app/gemini_pro.py` creates captions, narration, and dialogue and provides a procedural fallback.
- `app/image_generator.py` requests illustrations from Pollinations.ai, retries failures, and creates local placeholder PNGs when needed.
- `app/layout_builder.py` combines outline, script, and image paths into panel records.
- `app/exporters.py` formats the cover and panels into a PDF.
- `templates/` contains the form, preview, and export-success views.

## Panel Data Design

Each panel layout includes a panel number, title, scene description, image path, caption, narration, dialogue, combined text, and image prompt. The shared panel number and list order are used to align generated text and images.

## Storage Design

- Panel images are written to `static/panels/`.
- Exported comics are written to `static/exports/`.
- Both are served through FastAPI's `/static` mount.
- Generated files are runtime outputs, not required source files.