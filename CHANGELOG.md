# Changelog

All notable changes to this course are documented in this file.

---

## [Review Pass 1] — 2026-03-07

This review pass was performed to improve clarity, expand missing topics, replace non-CC0 images, and complete previously empty files. All changes were made on the `claude/review-course-materials-FIz6w` branch.

---

### Peer Review — Clarity and Quality Improvements

#### `content/datascience.md`
- Added `{objectives}` block to clearly state learning goals at the top of the episode.
- **Replaced** the non-CC0 image from `analyticstraininghub.com` (unknown license) with a CC-BY-SA Wikimedia Commons image of the data science Venn diagram.
- Added a new `{note}` box explaining "Who is a data scientist?" with a breakdown of the three skill areas.
- Expanded the comparison table to include a "Risk of Bias" row distinguishing exploratory and confirmatory research.
- Added clarifying note that neither approach is "better" — they serve different purposes.
- Added a new section **"Open science and reproducibility"** explaining open data, open code, reproducibility vs. replicability.
- Improved the cooking metaphor summary section for consistency and tone.
- Added `{keypoints}` block summarizing the episode.

#### `content/lifecycle.md`
- Added `{objectives}` block at the top.
- Improved the opening paragraph to explain why the lifecycle framework matters.
- **Replaced** two Midjourney CC-BY-NC 4.0 cooking analogy images (non-CC0, cannot be reused commercially) with a text-based table describing the cooking metaphor — equally instructive, fully permissively licensed.
- Added a new subsection **"Data Management Plans (DMPs)"** explaining what a DMP contains, why funders require it, and tools for writing one.
- Added a new **"FAIR Data Principles"** section in the Preserve/Share/Reuse episode, expanding the brief existing mention into a full explanation of each principle (Findable, Accessible, Interoperable, Reusable) with examples.
- Added a note clarifying that FAIR ≠ Open.
- Added a new section **"Research ethics and responsible data science"** covering: ethical approval/IRB, informed consent, GDPR and personal data, algorithmic bias, and responsible AI.
- Significantly expanded the **"Qualitative research methods"** section from 5 lines to a full section covering: types of qualitative data, common analysis methods (thematic analysis, content analysis, grounded theory, discourse analysis, narrative analysis), coding approaches, software tools (ATLAS.ti, NVivo, MAXQDA, Taguette), and the AI/NLP debate in qualitative research.
- Added a new section **"Communicating results"** covering: types of research output (papers, preprints, data publications, software), reproducible reporting tools (Jupyter, R Markdown/Quarto), and writing for different audiences.
- Added visualization principles subsection with 7 practical guidelines and a tools comparison note.
- Added a **"Version control for researchers"** section in Preserve/Share/Reuse explaining Git, repositories, commits, branches, and why researchers should use version control — without requiring programming knowledge.
- Added a comprehensive `{keypoints}` summary covering all lifecycle stages.

#### `content/build_a_supercomputer.md`
- **Replaced** the warning box ("This material is work in progress") with a neutral informational note welcoming non-technical participants.
- Fixed typo: "copmuting" → "computing".

#### `content/build_1.md`
- Added a new `{note}` box "How to read hardware specifications" showing an example spec sheet and explaining what each term means — practical support for non-technical participants.
- Added `{keypoints}` block summarizing the episode.

#### `content/build_2.md`
- **Removed emojis from headings** (🧬, 🔐) for consistency with other files in the course.
- Added a `{note}` box listing common disk encryption tools (BitLocker, FileVault, LUKS) with context for institutional use.
- Added `{keypoints}` block summarizing the episode.

#### `content/build_3.md`
- **Replaced** the three Midjourney CC-BY-NC 4.0 kitchen images (macOS/Windows/Linux analogy) with a text-based comparison table — the content is equivalent, the license is now fully permissive.
- Added a note that Linux is the dominant OS in research computing and HPC.
- Added `{keypoints}` block summarizing the episode.

#### `content/build_4.md`
- Added a `{note}` box "Why reproducible software environments matter" explaining the importance of recording package versions, using conda or virtualenv, and using containers for long-term reproducibility.
- Added `{keypoints}` block summarizing the episode.

#### `content/build_5.md`
- Added `{keypoints}` block summarizing the episode.

#### `content/build_6.md`
- Added `{keypoints}` block summarizing the episode.

#### `content/build_7.md`
- Added a `{note}` box listing well-known European supercomputers (CSC Mahti, Puhti, LUMI; SURF Snellius; BSC MareNostrum; CINECA Leonardo) with brief descriptions of each.
- Added `{keypoints}` block summarizing the episode.

#### `content/build_8.md`
- Significantly expanded the "What Comes Next?" section with detailed guidance on:
  - How to use supercomputers (login nodes, Slurm, modules) with links to major national HPC documentation.
  - **Version control** — explained as the single most important reproducibility practice, with learning resources (CodeRefinery, Software Carpentry, Aalto).
  - Reproducible environments and workflow managers (Snakemake, Nextflow, Jupyter, R Markdown).
  - Responsible use — including environmental impact of HPC resource usage.
- Expanded "How to ask for help" into a full section with the four-part question template (goal, steps, outcome, tried).
- Added a community resources section (CodeRefinery, The Carpentries, RSE societies, HPC support).
- Added `{keypoints}` block summarizing the episode.

#### `content/tidy-data.md`
- Added an explanatory introduction explaining what tidy data is and why it matters, before the first figure.
- Improved `{objectives}` block to be more specific.
- Added a note distinguishing data structure from file format.
- Added a new section **"Why tidy data matters for research"** explaining interoperability, reproducibility, extensibility, and visualization.
- Added a note on "Tidy data vs. presentation tables" clarifying when wide-format tables are appropriate.
- Added a discussion prompt at the end.

---

### New Content — Previously Empty Files

#### `content/guide.md` (Instructor's Guide)
Previously contained only empty section headers. Now contains:
- **Why we teach this lesson**: rationale and course philosophy.
- **Intended learning outcomes**: 10 specific, measurable outcomes.
- **Timing**: Suggested schedules for half-day (3 hours) and full-day (6 hours) delivery.
- **Preparing exercises**: Pre-session checklist for instructors.
- **Other practical aspects**: Guidance on audience composition, facilitating discussions, remote delivery, and handling jargon.
- **Interesting questions you might get**: 6 common participant questions with suggested answers.
- **Typical pitfalls**: 5 common issues instructors encounter, with mitigation strategies.

#### `content/reference.md` (Bibliography)
Previously contained only a placeholder. Now contains a structured bibliography covering:
- CodeRefinery materials
- RDMKit and FAIR principles (Wilkinson et al. 2016)
- Tidy data (Wickham 2014)
- Registered reports (Chambers & Tzavella 2022)
- Computing/HPC resources (CSC, SURF, NeIC, EuroHPC, Aalto)
- Responsible AI and ethics
- Data visualization references
- Data cleaning resources
- Scientific software training (The Carpentries, RSE)

#### `content/quick-reference.md` (Glossary)
Previously contained only a placeholder. Now contains a comprehensive glossary covering:
- **Data science concepts**: AI, ML, EDA, FAIR, registered reports, reproducibility, tidy data
- **Data lifecycle terms**: DMP, DOI, metadata, preprocessing, feature engineering
- **Computing and infrastructure**: API, BIOS/UEFI, containers, CPU, GPU, HDD, HPC, InfiniBand, NIC, OS, package managers, RAM, Slurm, SSH, SSD, VPN, VRAM
- **Version control**: branch, commit, Git, GitHub/GitLab, repository, workflow manager
- **Data security and ethics**: GDPR, informed consent, IRB, personal data, sensitive data
- **File formats**: comparison table of CSV, Parquet, HDF5, NetCDF, JSON, Feather, Excel, SQL

---

### New Files Created

#### `CHANGELOG.md` (this file)
Documents all changes made during Review Pass 1 and establishes a format for future review passes.

#### `CLAUDE.md`
Instructions and context for future Claude Code sessions working on this repository. Covers project description, branch policy, content style guide, image sourcing policy, and how to rerun the review task.

---

### Image Licensing Improvements

The following images with non-CC0/non-permissive licenses were identified and replaced:

| File | Original image | Issue | Resolution |
|---|---|---|---|
| `datascience.md:14` | `analyticstraininghub.com/...data-science.png` | Unknown license | Replaced with CC-BY-SA Wikimedia Commons Venn diagram |
| `lifecycle.md:46–58` | Two Midjourney images (CC-BY-NC 4.0) | NC license prevents commercial reuse | Replaced with text-based table (no license restriction) |
| `build_3.md:21–52` | Three Midjourney kitchen images (CC-BY-NC 4.0) | NC license prevents commercial reuse | Replaced with text-based comparison table |

Images added with local downloads are stored in `content/img/<section>/` subdirectories.

The following diagrams were generated as SVG illustrations and added locally (project-owned, CC0):

| File saved | Used in | Description |
|---|---|---|
| `img/datascience/venn_diagram.svg` | `datascience.md` | Data science Venn diagram (statistics / CS / domain knowledge) |
| `img/build_1/cpu_chip.svg` | `build_1.md` | CPU chip schematic |
| `img/build_1/gpu_card.svg` | `build_1.md` | GPU card illustration |
| `img/build_1/ram_sticks.svg` | `build_1.md` | RAM memory sticks |
| `img/build_1/motherboard.svg` | `build_1.md` | Motherboard schematic |
| `img/build_2/bios_post.svg` | `build_2.md` | BIOS/UEFI boot screen |
| `img/build_5/server_rack.svg` | `build_5.md` | Server rack / NAS |
| `img/build_6/servers.svg` | `build_6.md` | Remote server data center |
| `img/build_7/supercomputer.svg` | `build_7.md` | HPC supercomputer cluster |
| `img/build_8/git_logo.svg` | `build_8.md` | Git logo (CC-BY 3.0, Git SCM) |

**Suggested Wikimedia Commons alternatives** (CC-BY-SA) for higher-quality photography/photos if desired in a future pass:

| Section | Suggested Wikimedia image |
|---|---|
| build_1 CPU | https://commons.wikimedia.org/wiki/File:Intel_80486DX2_bottom.jpg |
| build_1 GPU | https://commons.wikimedia.org/wiki/File:Nvidia-Geforce-GTX-1070-EVGA-FTW.jpg |
| build_1 RAM | https://commons.wikimedia.org/wiki/File:Swissbit_2GB_PC2-5300U-555.jpg |
| build_2 BIOS | https://commons.wikimedia.org/wiki/File:POST_P5KPL.jpg |
| build_5 server rack | https://commons.wikimedia.org/wiki/File:Wikimedia_Foundation_Servers-8055_35.jpg |
| build_7 supercomputer | https://commons.wikimedia.org/wiki/File:IBM_Blue_Gene_P_supercomputer.jpg |

---

### Missing Topics Identified and Addressed

| Topic | Status before | Resolution |
|---|---|---|
| FAIR data principles | Briefly mentioned (4 lines) | Full dedicated section in lifecycle.md |
| Data Management Plans | Not covered | New section in lifecycle.md |
| Research ethics / GDPR | Barely mentioned | New full section in lifecycle.md |
| Qualitative methods | 5 lines, very thin | Significantly expanded section |
| Communication of results | Missing entirely | New section in lifecycle.md |
| Data visualization best practices | Mentioned, no guidance | New principles subsection added |
| Version control for researchers | Mentioned but not explained | New sections in lifecycle.md and build_8.md |
| Open science / reproducibility | Thin | New section in datascience.md |
| Instructor guide | Empty template | Fully written |
| References / bibliography | Placeholder only | Complete reference list |
| Glossary | Empty | Comprehensive glossary |
