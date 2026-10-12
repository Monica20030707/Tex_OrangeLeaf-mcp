# Cover Letter Customization Workflow

## 1. Fresh Initialization

Whenever a new job description is provided in `JobDesc.md`, start a fresh cover-letter run.

Read these files first:

- `templates/cover_letter_template.txt` for contact information and the required placeholder structure.
- `JobDesc.md` for the current role.
- Relevant YAML files in `knowledge/job/` and `knowledge/project/`, especially `bullet_variants`, for verified experience and project details.

Do not carry over company-specific wording, examples, or tailoring from a previous cover letter. Reuse the writing style and structure, not the previous application’s content.

Do not invent achievements, responsibilities, technical details, or metrics. If a source file is missing or a detail cannot be verified, do not assume it is true.

## 2. Analyze the Job and Select Relevant Evidence

Before drafting, identify:

- The company, position, and main responsibilities.
- The product, mission, or customer impact that genuinely stands out.
- The skills and qualities emphasized in the job description.
- The most relevant verified experience from the knowledge base.

Choose a few strong, relevant examples instead of trying to mention everything. Tailor the letter to the role while keeping the underlying facts accurate.

## 3. Positioning and Technical Accuracy

Present me as an early-career software engineer with practical development experience, a willingness to learn, and a focus on building useful, reliable software.

Relevant experience may include full-stack development, React, JavaScript/TypeScript, Node.js, APIs, external integrations, internal tools, AWS/cloud services, debugging, testing, performance, reliability, and scalability, but only when supported by the source material and relevant to the role.

Describe my actual contributions confidently without implying that I independently owned or shipped an entire product when I worked as part of a larger team. Do not inflate my seniority or technical ownership.

## 4. Tone and Writing Style

Keep the writing:

- Human, natural, and slightly conversational while remaining professional.
- Confident without sounding arrogant or overly polished.
- Curious, practical, persistent, and grounded in real experience.
- Specific to the company and role, without simply repeating the job description.

Avoid:

- Em dashes.
- Generic AI-generated phrases, filler, and corporate buzzwords.
- Exaggerated enthusiasm or unsupported claims.
- Repeating the same idea in multiple paragraphs.
- Turning the letter into a list of skills or a summary of my resume.
- Mentioning AI tools unless they are genuinely relevant to the role.

The letter should sound like a real person explaining why the role interests them and how their experience and mindset fit.

## 5. Required Four-Paragraph Structure

Use exactly four paragraphs.

### Paragraph 1: Opening and Interest

Start with this sentence, filling in the position name:

“I am a recent Computer Science graduate, and I am excited to apply for [Position Name].”

Then naturally explain what stands out about the company, its product, mission, or impact, and why that matters to me. Make the company reference specific and genuine rather than generic.

### Paragraph 2: Relevant Experience

Connect the most relevant parts of my verified experience to the role. Depending on the position, this may include full-stack development, React, APIs, backend work, integrations, or building applications for real users.

Emphasize the practical idea that getting software to work is only part of the job. It should also be stable, intuitive, and maintainable. Rephrase this idea naturally for each letter rather than repeating the exact same wording every time.

### Paragraph 3: Mindset and Approach

Describe how I approach problems and learning. Relevant themes include considering the user’s perspective, simplifying systems, automating repetitive work, being curious, verifying that things work in practice, and learning from teammates.

Choose only the themes that fit the role. Do not repeat the experience paragraph or turn this paragraph into a buzzword list.

### Paragraph 4: Closing

Keep the closing consistent in tone and meaning, making only small adjustments when needed for the company or position. Use this as the baseline:

“Thank you for considering my application. I’d love the chance to bring my curiosity, persistence, and hands-on verification mindset to [Company]. I don’t come from a flashy background, but I proved myself by shipping reliable work and learning fast. I’m excited to grow and contribute to a team doing meaningful work. Please feel free to contact me via email or phone should you have any questions or require additional information.”

Preserve the grounded, personal tone. Do not make the closing grander or more formal than the rest of the letter.

## 6. Consistency Across Applications

Keep the voice, four-paragraph structure, and overall personality consistent across cover letters. Vary the company details, selected experience, and technical examples to fit each role.

Consistency means the letters sound like the same person, not that every letter uses identical wording or the same project examples.

## 7. Final Quality Check

Before saving, confirm that:

- The letter has exactly four paragraphs.
- The opening sentence follows the required wording and includes the correct position name.
- The company and role references are accurate and specific.
- Technical details and accomplishments are supported by the source files.
- My contributions are represented accurately without overstating ownership or seniority.
- The letter sounds natural, human, and professional.
- There are no em dashes, generic filler, unnecessary buzzwords, or repeated ideas.
- The experience and examples are selected for this particular role.
- The closing keeps the intended tone.
- The final file is plain text content with no Markdown formatting.

## 8. Output File

Save each completed cover letter to:

`data/cover-letters/Thuy-<PositionShort>-<Company>-CoverLetter.txt`

Examples:

- `Thuy-SDE-Google-CoverLetter.txt`
- `Thuy-SWE-ExampleCompany-CoverLetter.txt`

Use a suitable position abbreviation, such as `SDE`, `ADE`, or `SWE`. Do not overwrite a cover letter for another company. If a file with the same name already exists, check before replacing it.

The cover letter itself should be plain text, without Markdown formatting. Report the saved file location when finished. If the file cannot be created, provide the letter in the response and clearly state that it was not saved.

## 9. Execution Trigger

When a new or updated `JobDesc.md` is provided:

1. Read the workflow instructions, template, and current job description.
2. Search the relevant job and project knowledge files for verified details.
3. Research the company when useful to make the opening specific and accurate.
4. Select the most relevant evidence for the role.
5. Draft the letter using the required four-paragraph structure and established tone.
6. Review it against the final quality checklist.
7. Save it using the required filename convention.
8. Report the result and file location.
