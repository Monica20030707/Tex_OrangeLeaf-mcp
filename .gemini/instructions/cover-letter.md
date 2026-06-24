# Cover Letter Customization Workflow

When a job description is provided in `JobDesc.md`, follow these steps to generate a tailored, human-sounding cover letter.

## 1. Fresh Initialization
- **Always** start by reading these instructions.
- **Never** use customizations, company names, or edits from previous runs. Each run must be a fresh start based on `templates/cover_letter_template.txt` (for contact info/placeholder structure) and the current `JobDesc.md`.
- **Tone:** Natural, human, and slightly conversational. Avoid sounding robotic, overly formal, or generic.

## 2. Analyze Job Description
- Extract the company name, position name, and key themes (e.g., scalability, user experience, automation, collaboration).
- **Knowledge Base Search:** Look through the YAML files in `knowledge/job/` and `knowledge/project/` to find specific achievements or "human" details that match these themes. Use the `bullet_variants` in those files to describe your work in a way that aligns with the job's focus (e.g., use the 'impact' variants for sales-heavy roles).
- Identify the company's mission or product impact to reference naturally.

## 3. Content & Tone Rules
- **Human Tone:** Use a professional but slightly casual voice. Sound like a real person, not a corporate bot.
- **Show, Don't Tell:** Instead of saying you are "skilled in X," use a detail from a `technical` or `impact` bullet variant in your knowledge base to *prove* it.
- **Style Constraints:** 
  - NO em dashes (—).
  - Avoid overly long sentences and filler phrases.
  - No markdown in the final output.
  - No buzzwords or generic phrases (e.g., "highly motivated," "passionate about technology").
- **Writing Style:** Confident but not arrogant; curious and growth-oriented.

## 4. Structure (4 Paragraphs ONLY)

### Paragraph 1: Opening (FIXED STRUCTURE)
- **Must start with:** "I am a recent Computer Science graduate, and I am excited to apply for [Position Name]."
- **Follow-up:** Include a natural reference to the company's product, mission, or impact. Show familiarity without sounding like a "research dump." Explain why they stand out to you, froma user perspective.

### Paragraph 2: Experience (SEMI-FIXED)
- **Focus:** Connect your real experience (Full-stack, React, APIs, backend) to the job requirements.
- **Emphasis:** Mention working on real applications/users, reliability, and usability.
- **Required Concept:** "Getting something working is not enough — making it stable, intuitive, and maintainable is what matters." (Rephrase naturally but keep the core idea).

### Paragraph 3: Mindset & Culture (FLEXIBLE)
- **Focus:** How you think (User perspective, simplifying systems, automation, curiosity, learning from others).
- **Optional:** Mention AI tools (Copilot, etc.) or collaboration if emphasized in the job description.
- **Avoid:** Repeating the resume or listing buzzwords.

### Paragraph 4: Closing (FIXED TEMPLATE)
- **Template:**
  > Thank you for considering my application. I’d love the chance to bring my curiosity, persistence, and hands-on verification mindset to [Company]. I don’t come from a flashy background, but I prove myself by shipping reliable work and learning fast. I’m excited to grow and contribute on a team doing meaningful work. Please feel free to contact me via email or phone should you have any questions or require additional information.
- **Note:** Only slightly tweak wording; do not change the tone or make it corporate.

## 5. Execution
- Create a new file using the following naming convention: `data/cover-letters/Thuy-<PositionShort>-<Company>-CoverLetter.txt` (e.g., `data/cover-letters/Thuy-SDE-Google-CoverLetter.txt`).
- Use standard abbreviations for PositionShort: SDE, ADE, SWE, etc.
- Perform a final check: Does it sound like a real person wrote it? Would you say it out loud?

---
*Note: This workflow is triggered by updates to `JobDesc.md`.*
