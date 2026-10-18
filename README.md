# Ravi Career Skills

A set of portable skills for evaluating job opportunities, tailoring truthful
resumes, and preparing company-specific research for Ravi's job search.

## Skills

| Skill | Purpose | Use it when |
| --- | --- | --- |
| [Ravi Job Fit Analyzer](./job-fit-analyzer/) | Scores a complete job posting against Ravi's verified career evidence, target roles, preferences, and constraints. | Deciding whether a role is worth applying to, investigating, or skipping. |
| [Ravi Resume Tailor](./resume-tailor/) | Creates a truthful, ATS-readable resume for an evaluated opportunity using approved evidence and strict anti-invention rules. | Customizing a resume for a specific job or target role. |
| [Ravi Company Researcher](./company-researcher/) | Produces a current, source-grounded company and role brief connected to Ravi's evidence and interview strategy. | Preparing to apply, network, interview, or speak with a hiring manager. |

## Recommended workflow

1. **Evaluate the opportunity** with [Ravi Job Fit Analyzer](./job-fit-analyzer/).
2. **Tailor the resume** with [Ravi Resume Tailor](./resume-tailor/) when the result is `APPLY` or `PRIORITY APPLY`.
3. **Research the company and role** with [Ravi Company Researcher](./company-researcher/) before applying, networking, or interviewing.

The workflow is evidence-first: use the latest user-approved Career Evidence
Bank and master resume, distinguish verified facts from interpretation, and do
not invent experience, scope, metrics, technologies, or outcomes.

## Repository structure

Each skill is self-contained and includes:

- `skill.md` — the skill definition, workflow, guardrails, and output rules;
- `README.md` — installation and usage notes;
- `references/` — authoritative frameworks, rules, templates, and evidence;
- `examples/` — examples of strong outputs and prohibited or weak patterns.

## Installation

Upload the individual skill folders as ZIP files to your AI assistant's
custom skills or customization area. Enable the skills together for the
recommended workflow. Start with a complete job posting and the latest
user-approved Career Evidence Bank.
