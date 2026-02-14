# game-design-document

**A community-created skill for Claude that generates professional, publisher-grade Game Design Documents.**

> **Note:** This is an independent, community-created project. It is not an official Anthropic product. It is designed to work as a skill with Claude (via Claude.ai, Claude Code, or the Anthropic API).

Turn any game concept — from a one-line idea to a half-developed vision — into a comprehensive 40-80 page Game Design Document in `.docx`, `.pdf`, and `.pptx` format. This skill conducts a structured discovery interview, generates a tailored outline for approval, then writes complete GDD content at a quality standard suitable for AAA studios, indie publishers, and investor pitches.

---

## What This Skill Generates

| Output | Format | Description |
|--------|--------|-------------|
| Full GDD | `.docx` | 40-80 page document with TOC, custom styles, tables, callout boxes |
| Full GDD | `.pdf` | Print-ready PDF for publisher/investor distribution |
| Pitch Deck | `.pptx` | 10-12 slide presentation for pitches and meetings |
| One-Page Pitch | `.pdf` | Single-page concept sheet for cold outreach |

**GDD Sections Covered (19 total):**
- Cover Page + Executive Summary
- Game Overview + Core Gameplay Loop
- Game Mechanics + Progression System
- Content Design + Narrative & World
- UX & Interface + Art Direction + Audio Design
- Multiplayer Design (if applicable)
- Monetization Strategy + Economy Design
- Technical Requirements + Competitive Analysis
- Development Roadmap + Risk Assessment + Appendices

**Supported Genres:** Roguelike, RPG, Action-Adventure, FPS/TPS, Strategy, Puzzle, Mobile F2P, Idle/Clicker, Sports, Simulation, Narrative Adventure, Battle Royale, VR/AR, and hybrids.

---

## Installation

### Claude.ai (claude.ai)

1. Download or clone this repository
2. Zip the `game-design-document/` folder: `zip -r game-design-document.zip game-design-document/`
3. Open Claude.ai → Settings → Skills
4. Click **Upload Skill** → select `game-design-document.zip`
5. The skill is now available in all conversations

### Claude Code (CLI or VS Code Extension)

```bash
git clone https://github.com/ityes22/game-design-document.git
cd game-design-document
```

Then open the folder in VS Code (or `cd` into it in the CLI). Claude reads the `CLAUDE.md` project instructions automatically and the skill is active. Just describe your game concept and it will start the GDD workflow.

### API Usage (Anthropic API)

Attach the `SKILL.md` content as a system prompt addition or use the Skills API endpoint:

```python
import anthropic

client = anthropic.Anthropic()

# Read the SKILL.md content
with open("game-design-document/SKILL.md", "r") as f:
    skill_content = f.read()

# Add to your system prompt
response = client.messages.create(
    model="claude-opus-4-6",
    max_tokens=8096,
    system=f"""You are a helpful assistant with the following skill active:

{skill_content}""",
    messages=[
        {"role": "user", "content": "I want to create a GDD for my roguelike deckbuilder game."}
    ]
)
```

---

## Usage

### Basic Usage

Simply describe your game concept and ask for a GDD:

```
"I want to create a GDD for my game. It's a roguelike deckbuilder set in a cyberpunk city."

"Help me write a game design document for a mobile RPG with gacha mechanics."

"Create a professional GDD for my competitive multiplayer shooter concept."

"I need a game design document for my indie puzzle platformer."
```

### Targeted Usage

Request specific sections or document types:

```
"Write just the mechanics specification for my card combat system."

"Generate a pitch deck for my game — I have a rough GDD already."

"Create a one-page pitch for my mobile game concept."

"Expand my existing mechanics doc into a full GDD."
```

### Workflow Example

The skill follows a 4-phase workflow:

**1. Discovery Interview**
The skill asks 2-3 focused batches of questions about your game concept. This takes 5-10 minutes but prevents re-work. Answer as specifically as you can.

**2. Outline Approval**
You receive a tailored 19-section outline. Review it, request changes, confirm sections to skip, and approve before full writing begins.

**3. Content Generation**
The skill writes each section at professional quality — specific numbers, design rationale, parameter tables, and designer notes. Expect 2,000-8,000 words per major section.

**4. Document Export**
Run the provided Python scripts to generate polished `.docx`, `.pdf`, and `.pptx` files ready for distribution.

---

## Python Script Dependencies

Install required packages before running export scripts:

```bash
pip install python-docx fpdf2 python-pptx
```

Or install via the pinned requirements file:
```bash
pip install -r requirements.txt
```

**Requires Python 3.10 or later.**

**Script usage:**
```bash
# Generate Word document
python scripts/generate_gdd_docx.py --title "My Game" --output "MyGame_GDD_v01.docx"

# Generate PDF
python scripts/generate_gdd_pdf.py --title "My Game" --output "MyGame_GDD_v01.pdf"

# Generate pitch deck
python scripts/generate_pitch_deck_pptx.py --title "My Game" --output "MyGame_Pitch.pptx"

# Generate one-pager
python scripts/generate_one_pager_pdf.py --title "My Game" --output "MyGame_OnePager.pdf"
```

---

## Customization

### Adding Custom Templates

Add custom section templates to `templates/` and reference them in the `SECTIONS` registry:

```python
# In scripts/utils/section_registry.py
SECTIONS["my_custom_section"] = {
    "name": "My Custom Section",
    "order": 20,
    "required": False,
    "min_words": 300,
    "key_elements": ["element1", "element2"],
    "template_file": "templates/my_custom_template.md"
}
```

### Modifying Document Styles

Edit `scripts/utils/docx_styles.py` to customize colors, fonts, and formatting:

```python
# Change primary brand color
COLORS = {
    "primary": "1A3C5E",      # Dark navy
    "accent": "E8B84B",        # Gold
    "callout_bg": "EEF4FB",   # Light blue callout background
    # ...
}
```

### Genre-Specific Configurations

The skill automatically adapts to genre, but you can pre-configure defaults by setting the genre in a session opener:

```
"I'm building a mobile F2P game. When I ask for GDD help, always start
with the mobile F2P template and expand monetization to 4+ pages."
```

---

## File Structure

```
game-design-document/
├── SKILL.md                              ← Skill entry point (install this)
├── LICENSE.txt                           ← Apache 2.0
├── README.md                             ← This file
│
├── templates/
│   ├── gdd_master_structure.md           ← Complete 19-section structure
│   ├── one_page_pitch_template.md        ← One-page concept sheet layout
│   ├── mechanics_specification_template.md ← Per-mechanic documentation
│   ├── ux_flow_template.md               ← Screen flow documentation
│   ├── monetization_strategy_template.md ← Revenue model templates
│   ├── technical_requirements_template.md ← Tech spec structure
│   ├── art_direction_template.md         ← Visual direction framework
│   └── competitive_analysis_template.md  ← Market analysis format
│
├── scripts/
│   ├── generate_gdd_docx.py              ← Word document generator
│   ├── generate_gdd_pdf.py               ← PDF generator
│   ├── generate_pitch_deck_pptx.py       ← PowerPoint pitch deck
│   ├── generate_one_pager_pdf.py         ← Single-page PDF
│   └── utils/
│       ├── docx_styles.py               ← Word document style definitions
│       ├── pdf_builder.py               ← PDF utility functions
│       ├── pptx_builder.py              ← PowerPoint utility functions
│       └── section_registry.py          ← GDD section registry
│
├── examples/
│   ├── example_roguelike_gdd_outline.md  ← Roguelike reference outline
│   ├── example_mobile_rpg_gdd_outline.md ← Mobile RPG reference outline
│   └── example_multiplayer_shooter_outline.md ← Shooter reference outline
│
└── assets/
    └── cover_page_spec.md               ← Cover page layout specification
```

---

## Example Output Quality

This skill generates GDD content at the level of published postmortems and publicly available studio documents. Example from a generated mechanics section:

> **Dodge Roll**
> **Category:** Core Movement
> **Input:** Hold [Left Stick] direction + press [Circle/B] during any non-stunned state
> **System:** Player becomes invincible for frames 3-11 of 20-frame animation. Moves character 4 meters in input direction. Consumes 1 Stamina point (max 3, regenerates 1 per 2.5s).
> **Feedback:** 10-frame afterimage trail (white, fading opacity), whoosh SFX, brief camera pull-back (0.05s)
> **Parameters:**
> | Parameter | Default | Min | Max | Notes |
> |-----------|---------|-----|-----|-------|
> | Invincibility frames | 3-11 | — | — | Fixed, not upgradeable |
> | Distance | 4.0m | 2.0m | 6.0m | Upgradeable via skill tree |
> | Stamina cost | 1 | 0 | 1 | Never free to preserve scarcity |
> | Stamina regen | 2.5s/point | 1.5s | 4.0s | Rebalanced per playtest |

---

## Contributing

Contributions welcome via pull request to [github.com/ityes22/game-design-document](https://github.com/ityes22/game-design-document).

Areas where contributions are especially valuable:
- Additional genre-specific example outlines (horror, sports, educational)
- Localization templates for non-English game documentation
- Additional Python script export formats (Markdown, HTML, Notion export)
- Improved pitch deck slide designs

Please review existing templates before contributing new ones to maintain consistency.

---

## Security

See [SECURITY.md](SECURITY.md) for vulnerability reporting and security practices.

## License

Apache License 2.0 — see [LICENSE.txt](LICENSE.txt)

This is a community project by [ityes22](https://github.com/ityes22). It is not an official Anthropic product.

This skill generates game design documentation frameworks. The generated documents belong to the user. All referenced game titles (Genshin Impact, Hades, Slay the Spire, etc.) are trademarks of their respective owners and are referenced for educational comparison purposes only. All example outlines contain fictional data — do not use example market statistics or KPIs without independent verification.

---

## Support

- Issues: [github.com/ityes22/game-design-document/issues](https://github.com/ityes22/game-design-document/issues)
- Claude Code: [docs.anthropic.com/en/docs/claude-code](https://docs.anthropic.com/en/docs/claude-code)
