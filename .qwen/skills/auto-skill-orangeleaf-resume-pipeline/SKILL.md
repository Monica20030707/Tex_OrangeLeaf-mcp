---
name: orangeleaf-resume-pipeline
description: Execute the full resume + cover letter generation pipeline when JobDesc.md is updated — read instructions, cross-reference knowledge base, generate tailored LaTeX and text files
source: auto-skill
extracted_at: '2026-06-25T05:46:29.567Z'
---

# OrangeLeaf Resume & Cover Letter Generation Pipeline

When the user updates `JobDesc.md` and asks you to "follow instructions and generate stuffs," execute this pipeline.

## Prerequisites

- The project is `Tex_OrangeLeaf-mcp` with structure: `knowledge/`, `.gemini/instructions/`, `.gemini/templates/`, `data/resumes/`, `data/cover-letters/`
- `JobDesc.md` contains the latest job description
- `knowledge/job/` and `knowledge/project/` contain YAML files for experiences and projects
- `.gemini/instructions/` has `resume.md` and `cover-letter.md` workflow docs
- `.gemini/templates/` has `resume_template.tex` and `cover_letter_template.txt`

## Pipeline Steps

### 1. Read All Sources
Read these files first to understand the full workflow:
- `README.md` — system architecture context
- `JobDesc.md` — current job description
- `.gemini/instructions/resume.md` — resume workflow rules
- `.gemini/instructions/cover-letter.md` — cover letter workflow rules
- `.gemini/templates/resume_template.tex` — base LaTeX template (never modify)
- `.gemini/templates/cover_letter_template.txt` — base letter template (reference only)

### 2. Read Knowledge Base
Read **all** YAML files in `knowledge/job/` and `knowledge/project/` to understand available content, including `bullet_variants` (technical, impact, leadership).

### 3. Analyze JD & Select Content

**Extract from JD:**
- Company name, position title, required skills, nice-to-haves
- Key themes (e.g., data-driven, full-stack, cloud, AI/ML)

**Select exactly 3 experiences and 2 projects:**
- Cross-reference JD requirements with YAML `tech_used` and `keywords` fields
- Prioritize entries with highest skill overlap
- For the selected entries, choose the best `bullet_variant`:
  - `technical` — for roles emphasizing engineering depth
  - `impact` — for sales/result-oriented roles
  - `leadership` — for senior/lead roles
  - Mix-and-match variants across bullets for the best narrative

**Handle title alignment:**
- If a JD title is close but not identical to a resume title (e.g., "backend engineer" vs "full stack software engineer"), tweak wording while preserving the same seniority level (intern, associate, junior, etc.)
- If multiple YAML entries share the same company and overlapping dates, pick the one with strongest relevance

**Update skills section:**
- Pull relevant keywords from `tech_used` and `keywords` of selected YAML entries that match the JD
- Keep the 3-line structure: Languages, Skills, Tools
- Do NOT create new sections

### 4. Generate Resume (.tex)

**Naming convention:** `data/resumes/Thuy-<PositionShort>-<Company>-Resume.tex`
- PositionShort: SDE, SWE, ADE, FSD, DS, etc. (standard abbreviations)
- Company: short name from JD (e.g., UST, Google)

**Template rules:**
- Copy `resume_template.tex` — never modify the original
- Uncomment selected experiences/projects (remove from `comment` blocks)
- Comment out non-selected entries (wrap in `\begin{comment}...\end{comment}`)
- Preserve exact LaTeX structure, margins, font, formatting
- Bold sparingly (~10% of doc) — bold only the most important metric/achievement per bullet
- **Must NOT exceed one page** — if too long, reduce bullets per entry to 2-3 and keep `\vspace` commands

### 5. Generate Cover Letter (.txt)

**Naming convention:** `data/cover-letters/Thuy-<PositionShort>-<Company>-CoverLetter.txt`

**Strict 4-paragraph structure:**
1. **Opening (FIXED):** Must start with "I am a recent Computer Science graduate, and I am excited to apply for [Position Name]." Then reference the company's mission/product naturally.
2. **Experience (SEMI-FIXED):** Connect real experience to JD requirements. Must naturally rephrase: "Getting something working is not enough — making it stable, intuitive, and maintainable is what matters."
3. **Mindset (FLEXIBLE):** How you think — user perspective, simplifying systems, automation, collaboration. Avoid repeating resume or listing buzzwords.
4. **Closing (FIXED TEMPLATE):** Follow the template closely with slight natural wording tweaks. No corporate tone.

**Style rules:**
- Human, conversational tone — sound like a real person
- NO em dashes (—), no markdown, no overly long sentences, no buzzwords
- "Show, don't tell" — use specific bullets from knowledge base to prove skills

### 6. Verification

- **Resume:** Check one-page limit, LaTeX syntax, correct uncomment/comment state, skills tailored, bold used sparingly
- **Cover letter:** Verify 4-paragraph structure, opening sentence, no em dashes, natural tone, closing template fidelity
- **Naming:** Both files follow the `Thuy-<PositionShort>-<Company>-<Type>` pattern

### 7. Final Note

Pushing the `.tex` file to GitHub triggers the automated LaTeX CI/CD workflow (`latex.yml`) — no local compilation needed.
