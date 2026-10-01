# 8. Project Demonstration

## Demonstration Goal

Show the complete journey from a short creative prompt to a five-panel illustrated comic and downloadable PDF.

## Suggested Walkthrough

1. Start the FastAPI app and open the home page.
2. Enter a premise, character name, setting, tone, and art style.
3. Submit the form and explain the five generated panels: outline, captions, narration, dialogue, and illustration.
4. Scroll through the preview and point out the exported PDF option.
5. Download and open the PDF to show the cover and panel pages.
6. Optionally show the JSON endpoint and explain the fallback behavior if AI services are unavailable.

## Demonstration Materials Already in the Workspace

- Screen recording: `Recording 2026-09-24 233301.mp4` (currently ignored by `.gitignore`).
- Example exported PDFs: root-level PDFs and files under `static/exports/` (currently ignored by `.gitignore`).
- Generated panel images: files under `static/panels/` (currently ignored by `.gitignore`).

These files remain in their existing locations and are not copied into this documentation folder. If the GitHub submission requires a recording or example outputs, add selected non-sensitive artifacts intentionally and review file size and repository policy first. Never include `.env` or API credentials.

## Demo Readiness Checklist

- Confirm dependencies are installed and the app starts.
- Confirm the chosen prompt can complete with available external services, or explain which fallback is being demonstrated.
- Confirm the preview shows five panels.
- Confirm the downloaded PDF opens.
- Avoid exposing API keys, local environment files, or unrelated generated outputs during screen sharing.