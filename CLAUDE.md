# Game Design Document Generator — Project Instructions

This project is a community-created skill for Claude that generates professional Game Design Documents.

## How This Skill Works

When a user describes a game concept or asks for a GDD, follow the complete instructions in `SKILL.md`. The skill has 4 mandatory phases:

1. **Discovery Interview** — Ask questions in batches to understand the game
2. **Outline Generation** — Present a tailored 19-section outline for approval
3. **Full Content Generation** — Write each section at publisher-grade quality
4. **Document Output** — Generate .docx, .pdf, .pptx files using the Python scripts

## First-Time Setup

If the virtual environment doesn't exist yet, create it:

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Running the Generators

Always use the project's virtual environment:

```bash
source .venv/bin/activate
python scripts/generate_gdd_docx.py --config game_config.json --output output/GameTitle_GDD.docx
python scripts/generate_gdd_pdf.py --config game_config.json --output output/GameTitle_GDD.pdf
python scripts/generate_pitch_deck_pptx.py --config game_config.json --output output/GameTitle_Pitch.pptx
python scripts/generate_one_pager_pdf.py --title "TITLE" --genre "Genre" --platform "Platform" --output output/GameTitle_OnePager.pdf
```

## JSON Config Format

When generating content, build a JSON config with these keys:

**Top-level metadata:** `game_title`, `tagline`, `genre`, `platform`, `audience`, `studio_name`, `version`, `date`, `lead_designer`

**Section content:** Use the `sections` dict with exact registry keys from SKILL.md. Each section value is either a string or `{"content": "...", "subsections": [...]}`.

## Key Rules

- Read `SKILL.md` for the complete skill instructions before generating any GDD
- Read template files from `templates/` when writing specific sections
- Read example files from `examples/` for genre-specific reference
- Use exact section registry keys (e.g., `monetization_strategy` not `monetization`)
- All Python scripts are in `scripts/` with utilities in `scripts/utils/`
- Dependencies are installed in `.venv/` (python-docx, fpdf2, python-pptx)
