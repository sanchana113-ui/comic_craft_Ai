# 1. Brainstorming & Ideation

## Idea

ComicCraft turns a short user idea into a personalized, illustrated five-panel comic that can be previewed in a browser and downloaded as a PDF. It combines AI-assisted writing with generated panel art so a user can move from a premise to a shareable comic in one workflow.

## Audience and Use Cases

- A beginner who wants to turn a character or story prompt into a short comic.
- A writer who wants a quick visual storyboard for an idea.
- A teacher, student, or family member creating a short themed story.

## Creative Inputs

- Story premise
- Main character name
- Setting
- Tone
- Art style

## Ideation Decisions

- Keep the initial story short and predictable at five panels.
- Make character, setting, tone, and art style configurable.
- Generate captions, narration, dialogue, and a visual prompt for every panel.
- Provide procedural text fallbacks when Gemini is not configured or unavailable.
- Provide a local placeholder illustration if the external image service fails.
- Make the result usable both as an in-browser preview and as a PDF.

## Implementation References

- Input form: `templates/index.html`
- Outline ideas and fallback panels: `app/gemini_flash.py`
- Script ideas and fallback dialogue: `app/gemini_pro.py`
- Illustration generation: `app/image_generator.py`