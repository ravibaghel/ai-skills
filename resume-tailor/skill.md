---
name: Ravi Resume Tailor
description: Tailor Ravi's resume to approved jobs using verified evidence, ATS-safe language, role positioning, evidence traces, and strict anti-invention rules.
---

# Ravi Resume Tailor

## Purpose

Create a truthful, targeted, ATS-readable resume for a specific job after the opportunity has been evaluated. Select, prioritize, and rephrase verified evidence without inventing experience, scope, metrics, authority, technologies, or outcomes.

This skill tailors a resume. It does not decide whether a job is worth applying to unless no prior Job Fit Report is available.

## Authoritative Inputs

Use these sources in priority order:

1. The latest user-approved master resume.
2. `references/career-evidence-bank.md` or a newer user-approved Career Evidence Bank.
3. The complete job description.
4. The Job Fit Analyzer report for that job.
5. New facts explicitly confirmed by Ravi.

Read these packaged resources:

- `references/tailoring-rules.md`
- `references/role-positioning.md`
- `references/evidence-guardrails.md`
- `references/ats-and-formatting.md`
- `references/output-template.md`
- `examples/good-transformations.md`
- `examples/prohibited-transformations.md`

If sources conflict, pause the affected claim, identify the conflict, and use the most recent user-approved fact. Never silently choose the more impressive version.

## When to Use

Use this skill when the user asks to:

- tailor or customize a resume for a particular job;
- rewrite a resume for one of Ravi's target roles;
- create an application-specific resume;
- align resume language with a job description;
- select achievements, skills, or projects for a role;
- improve ATS alignment for a specific posting;
- produce a resume change log or evidence trace.

Typical triggers:

- "Tailor my resume for this job."
- "Create a resume for this Application Manager role."
- "Use the fit report to customize my resume."
- "Make my resume ATS-friendly for this posting."

Do not invoke merely to evaluate whether Ravi should apply. Use the Job Fit Analyzer for that workflow.

## Preconditions

Before tailoring, ensure the following are available:

- complete job description;
- master resume content;
- Career Evidence Bank;
- preferably a Job Fit Report.

If the job description, master resume, or evidence bank is missing, return `STATUS: INPUT REQUIRED` and list the missing items. Do not fabricate a resume from partial memory.

## Job Fit Gate

If a Job Fit Report is supplied:

- PRIORITY APPLY: tailor fully.
- APPLY: tailor fully while clearly managing gaps.
- INVESTIGATE / NETWORK: do not create a final application resume unless the user explicitly asks to proceed. First state the unresolved issue.
- SKIP: do not tailor. Explain that the prior decision was Skip and ask for an explicit override before spending effort.

If no Job Fit Report is available, request or perform job-fit evaluation before final tailoring. A user may explicitly override this sequence.

## Core Principle

Tailoring means changing emphasis, ordering, terminology, and evidence selection. Tailoring does not mean changing history.

Allowed transformations:

- select the most relevant verified accomplishments;
- reorder bullets and sections;
- use job-relevant terminology when it accurately describes existing work;
- clarify business context;
- combine overlapping verified responsibilities without broadening scope;
- remove irrelevant or redundant content;
- convert passive phrases into concise action-result language;
- use approximate language for approximate evidence;
- surface genuine transferable experience as transferable.

Prohibited transformations:

- inventing accomplishments, technologies, domains, certifications, metrics, dates, authority, direct reports, budgets, or outcomes;
- replacing a job title with a target title;
- converting cross-functional coordination into formal people management;
- turning tool usage into platform architecture;
- turning a migration into a greenfield implementation;
- turning COTS/application experience into ERP, SAP, Workday, healthcare, or another domain without direct evidence;
- presenting preferred qualifications as possessed when unsupported;
- hiding a material gap by using ambiguous wording.
- do not use client company name anywhere in the resume.

## Workflow

### Step 1: Parse the job description

Extract:

- actual role purpose;
- top five to eight responsibilities;
- required qualifications;
- preferred qualifications;
- repeated keywords and concepts;
- implied seniority and leadership model;
- tools, platforms, methods, domains, and practical constraints.

Separate required from preferred qualifications.

### Step 2: Read the Job Fit Report

Identify:

- closest target role;
- decision and score;
- strongest direct evidence;
- transferable evidence;
- gaps and hard conflicts;
- job-specific prohibited claims;
- practical constraints that affect the application.

Do not use the fit score as an ATS score or success probability.

### Step 3: Build the evidence map

For each important job requirement, classify Ravi's support:

- A: direct evidence;
- B: supported evidence;
- C: transferable evidence;
- D: gap;
- X: conflict.

Only A and B evidence may be stated as established experience. C evidence must be framed as adjacent or transferable. D and X must not be concealed by resume language.

### Step 4: Select the positioning strategy

Choose one primary positioning lane from `references/role-positioning.md`.

Create:

- target headline;
- two to four summary themes;
- priority skills;
- flagship projects and accomplishments;
- content to shorten or remove.

Do not try to make one resume equally optimized for all six target roles.

### Step 5: Draft the resume

Default order:

1. Name and contact information copied exactly from the approved master resume.
2. Targeted professional headline.
3. Professional summary.
4. Core competencies or skills.
5. Professional experience.
6. Optional leadership/project highlights only when useful.
7. Education and certifications.

Preserve employer names, actual job titles, dates, locations, education facts, and certification status exactly unless the user corrects them.

### Step 6: Perform ATS alignment

Use important job-description terms only when supported by evidence. Prefer natural inclusion over keyword stuffing.

Do not add unsupported tools to a skills section merely because the posting names them.

Use standard headings and straightforward formatting. See `references/ats-and-formatting.md`.

### Step 7: Create an evidence trace

For every materially changed bullet or claim, record:

- final tailored text;
- original source or evidence ID;
- A/B/C classification;
- transformation type;
- confirmation that no new factual claim was introduced.

If a bullet cannot be traced, remove or mark it for user confirmation.

### Step 8: Run the anti-invention audit

Check every number, technology, responsibility, leadership claim, scope statement, and outcome against approved evidence.

Pay special attention to:

- team size;
- direct reports;
- formal management;
- budget and resource ownership;
- hiring authority;
- cloud and CI/CD ownership;
- AI, security, ERP, healthcare, SAP, Workday, and Kubernetes;
- greenfield claims;
- metrics and financial impact.

### Step 9: Deliver outputs

Follow `references/output-template.md`.

When a file is requested, produce a new file and do not overwrite the master resume. Use a descriptive filename such as:

`Ravi_Baghel_Resume_Technical_Delivery_Manager_Capgemini.docx`

## Writing Standards

- Use concise, natural US English.
- Begin bullets with strong verbs, but avoid exaggerated verbs such as transformed, revolutionized, or owned unless evidence supports them.
- Prefer specific nouns over vague leadership language.
- Do not use first person in the resume.
- Avoid keyword walls and repeated synonyms.
- Preserve accurate tense: present tense for current recurring responsibilities, past tense for completed work.
- Keep summary claims demonstrable through later experience bullets.
- Do not use em dashes.
- Maintain readable density and prioritization rather than forcing every keyword into the resume.

## Headline Rules

A headline may describe professional positioning but must not falsely replace the current formal title.

Allowed example:

`Technical Delivery Leader | Enterprise Applications, Cloud Platforms & API Integrations`

Not allowed:

`Technical Delivery Manager` when used in a way that falsely implies it is Ravi's current formal job title.

## Leadership Language

Supported language includes:

- led cross-functional delivery;
- coordinated approximately 8–10 engineering, product, and analysis participants;
- mentored engineers;
- conducted technical interviews and made hiring recommendations;
- presented status, risk, architecture, incident, and recommendation updates to senior stakeholders.

Unsupported language includes:

- managed 10 direct reports;
- conducted performance reviews;
- owned compensation or promotions;
- held final hiring authority;
- managed department budget;
- owned resource allocation.

## Technical Language

Supported:

- AWS production involvement with Compute, Storage, ECS, and AppStream;
- coordinated API and database-script deployments using Azure DevOps, Harness, and Jenkins;
- observability with Splunk, CloudWatch, Grafana, and AppDynamics;
- API and integration architecture;
- architecture recommendation to stagger calls in response to Seaware inventory slowness.

Unsupported without new evidence:

- architected the entire AWS environment;
- designed enterprise CI/CD platforms;
- Kubernetes delivery;
- security-delivery ownership;
- production AI-platform delivery;
- measured outcome from the staggered-call recommendation.

## Metrics

Use a metric only if:

1. it appears in an approved source;
2. the wording does not imply a more precise measurement than documented;
3. its context is sufficiently understood for the resume and likely interview follow-up.

Metrics with unclear measurement context should be flagged in the Evidence Trace. Do not invent a denominator, period, baseline, currency value, or causal explanation.

## Gap Handling

Do not write around a gap deceptively.

For a preferred but unsupported qualification, omit it and emphasize truthful adjacent evidence.

For a required unsupported qualification, state it in the Tailoring Strategy and Interview Risks. Do not add it to the resume.

For transferable evidence, use accurate framing such as:

- "related experience includes..."
- "adjacent delivery experience in..."
- "enterprise platform migration experience transferable to..."

The resume itself should remain concise; put explicit gap analysis in the supporting report, not as negative resume language.

## Quality Gate

Before delivering, confirm:

- The job is approved for tailoring or the user explicitly overrode the gate.
- The complete job description was used.
- Required and preferred qualifications stayed separate.
- The selected positioning lane matches the role's responsibilities.
- Employer names, titles, dates, and education facts were preserved.
- Every material claim traces to evidence.
- No direct-report, budget, performance-management, resource-planning, final-hiring, greenfield, AI, Kubernetes, ERP, domain, security, or ownership claim was invented.
- Approximate evidence remains approximate.
- Job-description keywords are used only where supported.
- The tailored resume remains readable and natural.
- The master resume was not overwritten.
- Evidence Trace and unsupported requirements are included.
