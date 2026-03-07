# CLAUDE.md — Instructions for Claude Code

This file provides context and instructions for Claude Code sessions working on this repository. It is intended to help future AI-assisted sessions understand the project and continue work effectively.

---

## Project Description

**Course title**: Introduction to Data Science and Data-Driven Research
**Author**: Enrico Glerean
**Affiliation**: Aalto University / CodeRefinery
**Format**: Sphinx-based documentation site (MyST markdown)
**Target audience**: Non-technical researchers and research support staff (data stewards, research managers, IT support)
**Course philosophy**: Conceptual, not hands-on. No code is taught. The course uses the "cooking metaphor" throughout.

---

## Repository Structure

```
datascience/
├── CHANGELOG.md           # Log of all changes
├── CLAUDE.md              # This file
├── README.md              # Minimal project readme
├── Makefile               # Sphinx build commands
├── requirements.txt       # Python dependencies (Sphinx, myst-nb, sphinx-lesson)
├── .github/workflows/     # CI/CD for automatic Sphinx build
└── content/               # All course content
    ├── conf.py            # Sphinx configuration
    ├── index.md           # Course homepage and navigation
    ├── datascience.md     # Episode 1: What is data science?
    ├── lifecycle.md       # Episode 2: Data science lifecycle
    ├── build_a_supercomputer.md  # Episode 3 hub: Building a supercomputer
    ├── build_1.md         # Step 1: Hardware components
    ├── build_2.md         # Step 2: BIOS/UEFI and firmware
    ├── build_3.md         # Step 3: Operating system
    ├── build_4.md         # Step 4: Software installation
    ├── build_5.md         # Step 5: Remote storage
    ├── build_6.md         # Step 6: Remote computing
    ├── build_7.md         # Step 7: Supercomputers / HPC
    ├── build_8.md         # Step 8: Next steps / celebration
    ├── tidy-data.md       # Extra: Tidy data and file formats
    ├── guide.md           # Instructor's guide
    ├── reference.md       # Bibliography and references
    ├── quick-reference.md # Glossary of key terms
    ├── css/style.css      # Custom styling
    └── img/               # Local image assets
        └── tidy-data/     # Images for tidy-data.md
```

---

## Branch Policy

**CRITICAL: Never push to `main` or `master`.**

All development must happen on dedicated branches starting with `claude/`. The current review branch is:

```
claude/review-course-materials-FIz6w
```

To push:
```bash
git push -u origin claude/review-course-materials-FIz6w
```

---

## Content Style Guide

### Tone and audience
- Written for **non-technical readers** — researchers and support staff with no assumed programming background.
- Clear, jargon-free language. When technical terms are necessary, define them immediately.
- Encouraging and accessible — never make readers feel the topic is beyond them.

### Cooking metaphor
The course uses a consistent cooking metaphor throughout:
- **Software / code** = Recipe
- **Data** = Ingredients
- **Libraries / packages** = Kitchen tools (pots, pans, blender)
- **Operating system** = Style of kitchen (the environment)
- **Hardware** = The kitchen itself (physical space)
- **CPU** = The chef
- **GPU** = Food processor (specialized and powerful)
- **RAM** = Kitchen counter (active workspace)
- **Storage** = Pantry / fridge (long-term storage)
- **NIC** = Delivery door (connects to the outside world)

Maintain and extend this metaphor when adding new content. Do not abandon it or introduce competing metaphors.

### MyST directives used
```
:::{objectives}     # Learning goals at the top of each episode
:::{discussion}     # Open-ended discussion prompts
:::{exercise}       # Hands-on activities
:::::{solution}     # Solution to an exercise (nested inside exercise)
:::{note}           # Additional context or deeper explanation
:::{warning}        # Important caution
:::{keypoints}      # Summary of key takeaways (end of each section)
```

Use `{objectives}` at the top of each episode and `{keypoints}` at the end.

### "Bonus insight for support teams" sections
Many files contain sections specifically addressing research support staff (data stewards, IT support). Preserve and expand these sections when editing.

### Headers
Use `##` for main sections, `###` for subsections. Do not use emoji in headers (they were removed during Review Pass 1 for consistency).

---

## Image Sourcing Policy

### License requirements
- **Preferred**: CC0 (public domain — no restrictions)
- **Acceptable**: CC-BY or CC-BY-SA (attribution required in caption)
- **Not acceptable**: CC-BY-NC (no commercial use), CC-BY-ND (no derivatives), or unknown/proprietary licenses

### Image sources
- **Primary**: [Wikimedia Commons](https://commons.wikimedia.org/) — excellent for hardware diagrams, scientific photos, technical illustrations
- **Secondary**: [OpenVerse](https://openverse.org/) with CC0 filter applied
- **Diagrams from Wikipedia**: Many SVG diagrams on Wikipedia are CC-BY-SA — acceptable with attribution

### Local vs. URL images
- **New images**: Download locally to `content/img/<section>/` (e.g., `content/img/build_1/cpu_chip.jpg`)
- **Existing URL images**: Leave as-is unless the license is problematic
- Midjourney images with CC-BY-NC 4.0 are NOT acceptable — replace with CC0 alternatives or text equivalents

### Figure syntax
```markdown
```{figure} img/build_1/cpu_chip.jpg
:alt: A close-up of an Intel CPU chip showing the gold connectors
:width: 70%

Intel CPU die. [Wikimedia Commons, CC-BY-SA 3.0]
```
```

---

## How to Rerun This Review Task

To perform another round of review, instruct Claude Code with a prompt like:

```
We need to continue reviewing the course materials:
1) Review any new content added since the last review
2) Search for CC0 images for sections still lacking visuals
3) Ensure all new content follows the cooking metaphor and style guide
4) Update CHANGELOG.md with a new dated entry
5) Work on branch claude/review-course-materials-FIz6w — never merge to main
```

Alternatively, for targeted improvements:
```
Focus on [specific file or topic].
Maintain the cooking metaphor, non-technical audience, and CC0-only image policy.
Update CHANGELOG.md and commit to claude/review-course-materials-FIz6w.
```

---

## Building the Documentation Locally

```bash
# Install dependencies
pip install -r requirements.txt

# Build HTML documentation
make html

# Or build with live reload (recommended for development)
make livehtml
# Then open http://localhost:8000 in your browser
```

The build output goes to `_build/html/`. Check for warnings — broken image paths and directive errors will appear in the build output.

---

## Commit Conventions

Use descriptive commit messages with a short prefix indicating the type of change:

```
peer-review: improve clarity of datascience.md intro
images: add CC0 CPU diagram to build_1.md
content: add FAIR principles section to lifecycle.md
fix: remove emojis from build_2.md headers
docs: complete guide.md instructor guide
```

Do not squash commits — individual commits are valuable for tracing what changed and why.

---

## Known Issues and Future Work

- Many sections would benefit from additional CC0 images (see CHANGELOG.md for which sections currently lack images).
- The `episode.md` file is a template/example — it should not be published as part of the course; consider removing from `index.md` toctree if present.
- `guide.rst-if-wanted`, `index.rst-if-wanted`, and `quick-reference.rst-if-wanted` are unused alternative format files — they can be deleted if the MyST markdown versions are considered final.
- The index.md may need updating after new content additions to ensure all files are included in the toctree.
- Consider adding a "Frequently Asked Questions" page based on the questions in `guide.md`.
