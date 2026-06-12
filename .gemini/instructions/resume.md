# Resume Customization Workflow

When a job description is provided in `JobDesc.md`, follow these steps to generate a tailored resume:

1.  **Fresh Initialization:**
    -   **Always** start by reading these instructions.
    -   **Never** use customizations, company names, or edits from previous job descriptions. Each run must be a fresh start based solely on `templates/resume_template.tex` and the current `JobDesc.md`.

2.  **Analyze Job Description:**
    -   Extract the company name and key requirements from `JobDesc.md`.
    -   **Knowledge Base Match:** Cross-reference requirements with the YAML files in `knowledge/job/` and `knowledge/project/`. Identify which experiences and projects have the highest keyword and skill overlap.
    -   If the company name is missing, use "Custom".

3.  **Template Integrity & Content Selection:**
    -   Use `templates/resume_template.tex` as the base template. **Never modify or overwrite `templates/resume_template.tex`.**
    -   **Content Selection Pool:** Select exactly **3 experiences** and **2 projects** from the template.
    -   **Smart Tailoring:** For the selected items, look up their corresponding YAML file in `knowledge/`. 
        -   If the job is highly technical, prioritize bullets from the `technical` variant.
        -   If the job emphasizes results or sales, use the `impact` variant.
        -   If the job is for a lead or senior role, use the `leadership` variant.
        -   Mix and match variants if needed to create the most compelling narrative for the specific role.
    -   **Skill Customization:** Update the "Skills" section (Languages, Skills, Tools) by pulling relevant keywords from the `tech_used` and `keywords` fields in the YAML files that match the `JobDesc.md`. Do NOT create new sections.
    -   **Formatting:** Maintain the **exact** LaTeX structure, formatting, margins, and style of `templates/resume_template.tex`.
    -   **One-Page Limit:** The final resume **MUST NOT** exceed one page. If the content is too long:
        -   Prioritize the most relevant bullet points.
        -   Reduce the number of bullet points per experience/project (aim for 2-3 high-impact bullets).
        -   Ensure `\vspace` commands from the template are preserved or adjusted slightly to save space, but do not change font size or margins.

4.  **Generate Customized LaTeX:**
    -   Create a new file using the following naming convention: `data/resumes/Thuy-<PositionShort>-<Company>-Resume.tex` (e.g., `data/resumes/Thuy-SDE-Google-Resume.tex`).
    -   Use standard abbreviations for PositionShort: SDE (Software Development Engineer), ADE (Associate Developer/Engineer), SWE (Software Engineer), DS (Data Scientist), etc.
    -   Uncomment selected experiences/projects if they were commented in the original, and comment out the ones not selected.

5.  **GitHub Workflow & PDF Management:**
    -   Ensure a `data/resumes/` subdirectory exists for `.tex` files and a `data/pdfs/` subdirectory exists for generated PDFs.
    -   Pushing a new `.tex` file to GitHub will trigger an automated workflow.
    -   The workflow will compile all `.tex` files from the `data/resumes/` directory and save the resulting PDFs into the `data/pdfs/` directory.

---
*Note: This workflow is triggered by updates to `JobDesc.md`.*

