# ComicCraft Project Files

This folder organizes the ComicCraft project by its eight development phases. Each phase has a focused document describing the work and linking it to the current implementation.

## Phase Documents

1. [Brainstorming & Ideation](01-brainstorming-and-ideation.md)
2. [Requirement Analysis](02-requirement-analysis.md)
3. [Project Design Phase](03-project-design.md)
4. [Project Planning Phase](04-project-planning.md)
5. [Project Development Phase](05-project-development.md)
6. [Project Testing](06-project-testing.md)
7. [Project Documentation](07-project-documentation.md)
8. [Project Demonstration](08-project-demonstration.md)

## Source Files

The application source stays in its existing locations so Python imports and static/template paths continue to work. The phase documents map each part of the project to its implementation. Main locations are:

- `app/`: FastAPI application, routes, AI integrations, layout assembly, and PDF export.
- `templates/`: Comic generator form, comic preview, and export confirmation pages.
- `static/`: Generated comic panel images and exported PDFs.
- `test_pipeline.py`: Pipeline, export, and API integration tests.
- `requirements.txt`: Python dependencies.

Generated PDFs, panel images, local environment files, and the demo recording are excluded by the repository's current `.gitignore` rules. Add any demo artifacts to a GitHub upload deliberately if they should be tracked; do not upload `.env` or API tokens.

## Project Summary

ComicCraft is a web application for creating personalized five-panel comics. Users provide a story premise and creative options; the app creates an outline and script, generates an illustration for each panel, assembles a preview, and exports a PDF. Gemini is used for text generation when configured, Pollinations.ai is used for panel illustrations, and local procedural fallbacks keep parts of the pipeline usable when services are unavailable.