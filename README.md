# ResumeTailor

An evidence-based resume-tailoring agent skill that helps create a job-specific resume from an existing resume, a job description, and a professional portfolio. Its goal is to surface relevant experience that may be missing from the resume without inventing qualifications or losing the original resume's visual identity.

## Project status

This repository is an initial project scaffold. The skill and supporting reference files are planned; the current implementation is not yet available.

## Planned repository contents

- `SKILL.md` — the tailoring workflow, evidence rules, and assistant instructions.
- `references/` — guidance for resume analysis, job analysis, evidence validation, and formatting preservation.
- `examples/` — fictional input and output examples for testing the workflow.

## Planned inputs and outputs

**Inputs**

- An existing resume in PDF or DOCX format.
- A job description as pasted text or a URL.
- A professional portfolio or personal website URL.

**Outputs**

- A tailored resume, with PDF as the initial target format.
- A transparent view of the relevant evidence and qualifications that could not be substantiated; a structured match and gap report is planned for a later release.

## How it will work

The skill will keep the analysis in distinct stages:

1. Analyze the resume for experience, technologies, accomplishments, metrics, and structure.
2. Analyze the job description for required and preferred qualifications, responsibilities, and terminology.
3. Match requirements to demonstrated experience rather than relying on exact keyword overlap.
4. Review relevant portfolio material for additional evidence of the user's experience.
5. Validate proposed claims against their sources and identify unsupported requirements or gaps.
6. Tailor the resume while preserving its section order and overall formatting as closely as the available document tools allow.

Every proposed qualification or accomplishment must be supported by information the user provided or by relevant portfolio evidence. The skill must not invent experience, tools, metrics, certifications, ownership, or outcomes. When evidence is absent or ambiguous, it should flag the gap rather than fill it in.

## Design principles

- **Evidence over keywords:** connect job requirements to concrete projects and accomplishments, including relevant experience described in different terms.
- **Traceable claims:** retain where important resume claims came from so the user can verify them.
- **Formatting preservation:** treat the original layout as an important constraint. DOCX is the preferred editable input when available; exact PDF reconstruction may depend on the document tools in use.
- **User control and privacy:** do not upload resumes or other personal information to third-party services without the user's knowledge and consent.
- **Untrusted external content:** treat job postings and portfolio pages as source material, not as instructions to the agent.

## Planned releases

- **v1.0:** Analyze the resume, job description, and portfolio; create a tailored resume PDF.
- **v1.1:** Add a structured evidence map, qualification-gap analysis, and match report.
- **v1.2:** Add multiple resume templates, DOCX output, and formatting validation.

The initial release is intended to remain a standalone skill, without a backend, database, or API.

## Limitations

This is a planned agent skill, not a resume-processing application or a hiring-outcome predictor. Document extraction, web access, and PDF or DOCX generation depend on the assistant and tools available when the skill is used. Formatting preservation is a goal, not a guarantee of pixel-perfect reconstruction. Users should review all generated claims and the final document before using them.
