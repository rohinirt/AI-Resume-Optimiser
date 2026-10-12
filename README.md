# Changelog

All notable changes to the Resume Optimiser, newest first. Versions are labelled after the fact from the project history. Exact dates were not recorded before 6 Oct 2026, so earlier versions are listed as "before 6 Oct".

## v0.8.1 – 12 Oct 2026
**Fixed**
- "Found in your experience" check wrongly showed "Not found in your extra files" for skills that are in the files. Cause: it matched the AI's answers back to gaps by exact label text.
- Gaps now have IDs and are checked 10 at a time. Several reply shapes are accepted.
- The prompt now counts close equivalents (MySQL for database management, permission and row-level access issues for access controls).
- Cards say "Could not check this one" when a check fails, instead of "Not found".
- A line under the score breakdown shows how many gaps were checked and how many have support.

## v0.8 – 10 Oct 2026
**Added**
- Evidence search: after Analyse, missing and partial skill and narrative points are searched in the Extra experience and Projects files. Matches show a quote, where it came from, and a rewrite plan.
- The rewrite prompt includes this evidence and applies it (source tagged "experience file").
- After a rewrite, the Skills and Narrative lists show the re-scored resume with "Newly matched by rewrite" and "Improved by rewrite" tags.

**Changed**
- Browser-key mode restored next to the server mode (see v0.7). With the `PROXY` line unset, visitors paste their own key, as before.

## v0.7 – 8 Oct 2026
**Added**
- Optional server mode: `worker/worker.js` (Cloudflare Worker) keeps the Gemini key secret. Set the `PROXY` line in `index.html` to hide the key box and leave only the model dropdown.
- Worker only accepts your site's origin, only allows Gemini model calls, and caps request size.

**Changed**
- Bullet rule relaxed: by default a role keeps the resume's bullet count. The AI may add up to 2 per role (never above 6) when the job or a note needs it. It may still cut weak bullets (minimum 3 per role).

## v0.6 – 6 Oct 2026
**Added**
- "I have this" notes on missing and partial Skills and Narrative points. The rewrite treats them as true evidence.
- Extra experience and Projects inputs are optional. The app works from the resume and job description alone.
- Generic roles: every job on the resume is handled, nothing is hard-coded to a company.
- Bullets ordered by relevance and impact for the job, with an "Order" reason.
- Download name `Name_Resume_Company_Role` (company left out if the JD does not name it).

## v0.5 – before 6 Oct
**Fixed**
- Score dropped after a rewrite because only rewritten sections were scored. The whole updated resume is now re-scored.
- Added ATS TARGETS (keywords to keep and to add if true) and KEYWORD SAFETY to the rewrite prompt.
- Added a list of keywords the rewrite dropped, one automatic repair pass, and a warning banner if the score is still lower.
- Rewrite quality rules: strong action verbs, concrete results, no invented numbers.

## v0.4 – before 6 Oct
**Added**
- Workday-style scoring engine: the AI only extracts data. Skills (40%) use the ESCO skill ontology, Title (25%) and Narrative (15%) use in-browser meaning-based matching, Hard requirements (20%) are checked exactly (years, degree, certifications).
- Fallback to an AI estimate if the engine cannot run.

## v0.3 – before 6 Oct
**Added / fixed**
- Standalone GitHub Pages site using the free Gemini API, with a model dropdown and automatic model discovery (fixes retired-model 404s).
- Retry and back-off on busy (503) and rate-limit (429) replies.
- Project hyperlinks are read correctly and kept as real links.
- Description text no longer clipped; keyword table counts; KPI shows percentages only; quality-check box removed; analysis resets on re-analyse.

## v0.2 – before 6 Oct
**Added**
- Upload resume (.docx), experience, projects and job description. ATS match score with deep analysis (hidden by default), rewrite of summary, experience bullets, projects and skills, with What / Why / How for each change.
- Word download keeps original formatting, with job keywords in bold. PDF download.
- Limits: summary 40–60 words, 1–2 bullets per project.

## v0.1 – before 6 Oct
**Added**
- First version: a Claude-powered artifact on claude.ai (AI-estimated scores).
- Earlier Next.js prototype of the scoring pipeline (`resume-engine`).

## Known limits
- Workday does not publish its scoring formula, so scores are a guide, not a prediction.
- The "Current match" score reflects the uploaded resume only. Experience files and notes affect the rewrite, and the "After rewrite" score.
- The shared free Gemini quota applies to every visitor in server mode.
