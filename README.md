# OrangeLeaf-mcp: Automated Resume Generation Pipeline

This is a system for programmatically generating tailored resumes and cover letters. Instead of manual document editing, this project treats professional experience as a versioned data source and uses a CI/CD pipeline to output formatted PDFs.

## System Architecture

The system follows a "Separation of Concerns" pattern:
1.  **Data Layer**: Professional experience is stored as schema-validated YAML objects in `/knowledge`. Each entry supports multiple attribute variants (Technical, Impact, Leadership) to allow for dynamic content injection.
2.  **Orchestration Engine**: LLM-driven logic in `.copilot/` parses `JobDesc.md` to perform feature extraction and cross-reference the data layer for optimal content selection.
3.  **Presentation Layer**: LaTeX templates manage the typesetting and layout, ensuring consistent output regardless of content changes.

## The Pipeline

1.  **Input**: Paste the target job description into `JobDesc.md`.
2.  **Tailoring**: The system analyzes the JD, cross-references my `knowledge/` base, and selects the 3 experiences and 2 projects that maximize keyword/skill overlap.
3.  **Generation**: Tailored `.tex` (resume) and `.txt` (cover letter) files are generated in the `data/` directory.
4.  **Auto-Compile**: Pushing a new `.tex` file triggers a GitHub Action that runs a LaTeX build and saves the final PDF to `data/pdfs/`.

## Design Advantages

*   **Version Controlled**: Every iteration of a resume is a git commit. This enables diffing between different role-specific versions (e.g., Sales Engineer vs. Backend Engineer).
*   **Natural Language Generation**: The cover letter engine is configured with strict constraints to avoid generic corporate jargon, focusing instead on verifiable achievements and technical problem-solving.
*   **Deterministic Formatting**: LaTeX ensures pixel-perfect, consistent typesetting. The build process guarantees that formatting remains intact regardless of content length or complexity.
*   **Dynamic Content Mapping**: Professional history is maintained in a modular YAML format, allowing the system to automatically map the most relevant "flavor" of an experience to the job requirements.

## Repository Map

*   `knowledge/`: The data layer (YAML files for every job/project).
*   `.copilot/`: The "compiler" settings and templates.
*   `data/resumes/`: Generated LaTeX source files.
*   `data/pdfs/`: Final build artifacts.
*   `JobDesc.md`: The input buffer for the next tailoring run.

## Usage

1.  Populate `knowledge/` using the provided YAML templates.
2.  Paste a JD into `JobDesc.md`.
3.  Trigger the tailoring workflow to generate the files.
4.  Check `data/pdfs/` for the compiled output.

---
*Built to minimize manual overhead. Compiled by GitHub Actions.*
