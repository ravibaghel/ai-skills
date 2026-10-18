---
name: Ravi Job Fit Analyzer
description: Evaluate job postings against Ravi's verified career evidence, target roles, preferences, constraints, and scoring rules before applying.
---

# Ravi Job Fit Analyzer

## Purpose

Evaluate whether a job opportunity deserves Ravi Baghel's time. Produce an evidence-grounded fit score and a clear decision before any resume tailoring, networking, or interview preparation begins.

This skill is an evaluation skill, not a resume-writing skill. Do not tailor a resume unless a separate resume-tailoring workflow is requested after the evaluation.

## Authoritative References

Read the following files when performing an evaluation:

1. `references/career-evidence-bank.md` for verified and user-confirmed career evidence.
2. `references/target-role-matrix.md` for role-specific evaluation criteria.
3. `references/scoring-model.md` for weights, penalties, thresholds, and confidence rules.
4. `references/evidence-rules.md` for evidence classifications and hard claim guardrails.
5. `references/output-template.md` for the required response structure.

If a newer Career Evidence Bank is present in the user's connected career folder, prefer the newest user-approved version and state which version was used.

## When to Use

Use this skill when the user asks to:

- evaluate a job, role, vacancy, posting, or job description;
- decide whether to apply;
- assess fit, match, suitability, or alignment;
- compare a job against Ravi's background;
- rank or prioritize multiple job opportunities;
- identify gaps, red flags, interview risks, or transferable experience;
- determine which target role a posting most closely resembles.

Typical triggers include:

- "Should I apply?"
- "Evaluate this job."
- "Is this a good fit?"
- "Analyze this JD."
- "Compare this role with my experience."
- "Score this position."
- "Is this worth my time?"

Do not use this skill merely to write a resume, cover letter, networking message, or interview answer unless job-fit evaluation is also requested.

## Target Roles

Evaluate opportunities against these target roles:

1. Application Manager
2. Technical Delivery Manager
3. Information Technology Manager
4. Information System Manager
5. Software Engineering Manager
6. Technical Services Manager

Score the actual responsibilities before the title. A familiar title does not guarantee fit, and an unfamiliar title may still match a target role.

## Required Inputs

A valid evaluation requires enough of the actual job description to identify:

- company and role;
- location and work arrangement, when published;
- primary responsibilities;
- required qualifications;
- preferred qualifications;
- compensation, when published;
- work-authorization or travel requirements, when published.

A title or URL without retrievable job content is insufficient.

## Insufficient-Data Rule

Never calculate a fit score from a title, URL slug, search snippet, or incomplete posting alone.

If the actual job description is unavailable, return:

```text
STATUS: INSUFFICIENT DATA

Missing:
- Responsibilities
- Required qualifications
- Preferred qualifications

Next input needed:
Paste or attach the complete job description.

Do not generate a fit score.
```

If only one section is missing, identify that section and explain how the omission limits confidence. Do not invent missing requirements.

## Evaluation Workflow

Follow these steps in order.

### Step 1: Verify the posting

Confirm that the job content being evaluated corresponds to the stated company and role. Prefer the employer's official posting when available. If multiple versions conflict, identify the conflict and avoid silently combining them.

### Step 2: Extract facts

Separate the posting into:

- core responsibilities;
- required qualifications;
- preferred qualifications;
- practical constraints;
- compensation and location information;
- implied seniority and scope.

Do not convert preferred qualifications into requirements. Do not downgrade explicit requirements to preferences.

### Step 3: Determine the closest target role

Select the closest primary target role. Add a secondary target role only when the responsibilities genuinely span two tracks.

Use the role matrix rather than title matching.

### Step 4: Map every material requirement to evidence

For each material requirement, identify:

- the requirement;
- evidence classification: A, B, C, D, or X;
- the exact supporting project, responsibility, metric, or artifact;
- impact on application viability: Low, Medium, High, or Critical.

Use only evidence in the Career Evidence Bank or newer facts explicitly supplied by the user.

### Step 5: Score using the closest role model

Apply the relevant role-specific weights from `references/scoring-model.md`.

Award points for demonstrated match, not keyword presence. A technology listed in a skills section is weaker than a concrete project involving that technology.

### Step 6: Apply penalties

Apply penalties only after calculating the positive alignment score.

Penalize:

- unsupported explicit requirements;
- hard conflicts;
- a mandatory qualification supported only by transferable evidence;
- formal people-management requirements when only cross-functional leadership is documented;
- budget or resource ownership when unsupported;
- practical constraints such as location, work authorization, travel, or compensation when clearly incompatible.

Do not double-penalize the same gap under multiple categories.

### Step 7: Set confidence

Set confidence independently from fit:

- HIGH: Complete posting and strong evidence coverage; few assumptions.
- MEDIUM: Posting is usable but some material responsibilities, constraints, or evidence are unclear.
- LOW: Posting is incomplete or key requirements are ambiguous. If the posting is too incomplete to score, use INSUFFICIENT DATA instead.

A high fit score may still have low confidence. A low fit score may have high confidence.

### Step 8: Make the decision

Use these thresholds unless a Critical hard conflict overrides them:

- 85–100: PRIORITY APPLY
- 75–84: APPLY
- 65–74: INVESTIGATE / NETWORK
- Below 65: SKIP

A Critical conflict may override the numerical threshold. Explain the override explicitly.

### Step 9: Recommend next action

For PRIORITY APPLY or APPLY:

- identify the three to five strongest pieces of resume evidence;
- identify likely interview risks;
- state any point that must be clarified before submission.

For INVESTIGATE / NETWORK:

- identify the exact blocking uncertainty;
- propose the one or two questions that would change the decision;
- do not recommend extensive tailoring until those questions are resolved.

For SKIP:

- explain the principal mismatch concisely;
- identify whether the posting should be archived or reconsidered only if a specific fact changes.

## Evidence Classification

Use these labels exactly:

- **A | Direct evidence:** A specific project, responsibility, result, metric, or artifact directly supports the requirement.
- **B | Supported evidence:** The background supports the requirement, but the Career Evidence Bank lacks a complete example or artifact.
- **C | Transferable evidence:** Adjacent experience may transfer, but it is not equivalent.
- **D | Gap:** No current evidence supports the requirement.
- **X | Hard conflict:** The requirement materially conflicts with documented experience or a practical constraint.

Never upgrade C to B or D to C simply to improve the score.

## Claim Discipline

Always distinguish among:

- facts stated in the job posting;
- facts supported by Ravi's Career Evidence Bank;
- user-provided estimates;
- analyst judgment;
- unknown information.

Use approximate language for estimates. Do not convert "approximately 8–10" into an exact team size.

Never present the calculated fit score as an employer score, ATS score, probability of interview, or probability of offer. It is a prioritization model for Ravi's job search.

## Hard Guardrails

Never invent or imply:

- formal direct reports;
- formal people-management experience;
- performance-review or goal-setting ownership;
- budget ownership;
- resource-planning ownership;
- final hiring authority;
- a production AI-platform delivery;
- greenfield delivery unless evidence is supplied;
- Kubernetes experience unless evidence is supplied;
- CI/CD pipeline architecture;
- personal construction of the entire AWS environment;
- security-delivery ownership unless evidence is supplied;
- quantified savings, revenue, uptime, reliability, satisfaction, or other impact without documented support;
- ERP, healthcare, Workday, SAP, or regulated-industry experience by analogy alone.

Cross-functional leadership must not be rewritten as direct people management.

## Supported Positioning

Current supported themes include:

- cross-functional technical-delivery leadership;
- enterprise COTS application lifecycle;
- application enhancements, releases, incidents, integrations, architecture, and support;
- schedules, dependencies, risks, releases, validation, production readiness, and hypercare;
- ITSM, SLA, incident, change, problem-management, service-review, and RCA practices;
- API and integration architecture;
- AWS production involvement;
- deployment coordination using Azure DevOps, Harness, and Jenkins;
- observability using Splunk, CloudWatch, Grafana, and AppDynamics;
- executive stakeholder communication;
- mentoring and technical interviewing with hiring recommendations;
- legacy-platform migration and phased cutover.

## Practical-Constraint Rules

### Work authorization

If the posting explicitly excludes current or future sponsorship and Ravi's compatibility is unknown, mark it as a clarification required. Do not infer immigration status.

If the user confirms incompatibility, classify it X and treat it as a Critical conflict.

### Location and work arrangement

Use only published location/work-arrangement facts and the user's confirmed preferences. Do not assume that a listed office means remote or hybrid.

### Compensation

Report compensation only when published. Do not estimate missing compensation. Compare it to user preferences only when those preferences have been explicitly supplied.

### Travel

If travel is required but the user's tolerance is unknown, flag it for clarification rather than penalizing heavily.

## Multiple-Job Comparison

When comparing postings:

1. Evaluate each job independently before ranking them.
2. Use the same evidence rules and applicable role weights.
3. Do not force equal scoring dimensions when postings map to different target roles.
4. Rank by decision category first, adjusted score second, confidence third, and practical feasibility fourth.
5. Explain why a lower raw score might still be strategically better if the evidence is stronger or practical constraints are safer.

## Calibration Examples

Use `examples/calibration-cases.md` as behavioral guidance, not as permanent scores. Recalculate if the posting or Career Evidence Bank changes.

## Required Output

Follow `references/output-template.md`. Keep the report candid, evidence-grounded, and useful for a decision.

The opening must give:

- overall fit score;
- confidence;
- decision;
- one-paragraph explanation.

Then provide evidence mapping, gaps, hard conflicts, practical constraints, interview risks, positioning, resume evidence to emphasize, and prohibited claims.

## Quality Check Before Responding

Confirm all of the following:

- The complete posting was available, or INSUFFICIENT DATA was returned.
- Required and preferred qualifications were kept separate.
- The closest target role was selected from responsibilities, not title alone.
- All material requirements were classified A/B/C/D/X.
- Every claimed match points to actual evidence.
- No unsupported management, budget, resource, AI, cloud, security, or domain claim was added.
- Penalties were not duplicated.
- Fit and confidence were reported separately.
- Practical constraints were included.
- The final decision matches the threshold or the override is explained.
- The response tells Ravi what to do next.
