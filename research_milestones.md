# Research Milestones

## Website CV Synchronization

**Date:** 2026-05-13

**Long-term research goal:** Keep the personal website aligned with Jianhong Tu's current research identity and output so visitors can quickly understand the trajectory across foundation models, post-training, agentic AI, and cybersecurity.

**Hypothesis:** Updating the website from the canonical CV PDF/TeX source will reduce stale public-facing information and make the homepage, CV page, and publications list mutually consistent.

**Method:** Use `assets/pdf/jianhongtu_CV.tex` as the structured source for website content, keep `assets/pdf/jianhongtu_CV.pdf` as the downloadable artifact, and mirror the relevant CV entries into al-folio's `resume.json` and bibliography data.

**Tradeoffs:**

- Pros: The website CV page becomes searchable, readable, and consistent with the PDF.
- Pros: The publications page reflects recent 2026 work instead of lagging behind the CV.
- Cons: CV information is duplicated across TeX, JSON, and BibTeX, so future updates should sync all three.

**Observations:**

- The homepage already linked to `jianhongtu_CV.pdf`.
- The `/cv/` page still pointed to `example_pdf.pdf`.
- `assets/json/resume.json` still contained al-folio's Albert Einstein sample data.
- `_bibliography/papers.bib` was missing multiple publications listed in the new CV.

**Outcome:** Verified with a full Jekyll build in Docker. Generated HTML includes the updated homepage bio, the `jianhongtu_CV.pdf` download link on `/cv/`, structured CV content from `resume.json`, and the new 2026 bibliography entries.

**Follow-up observation:** The resume templates linked item titles even when a JSON entry had no URL. The templates now render plain text in that case, avoiding empty links on the CV page.

## CV TeX Consistency Pass

**Date:** 2026-05-13

**Hypothesis:** Treating the updated `assets/pdf/jianhongtu_CV.tex` as the source of truth should remove drift introduced while syncing the website from an earlier CV version.

**Method:** Re-compare the TeX CV against `assets/json/resume.json`, `_bibliography/papers.bib`, and the homepage. Patch only direct inconsistencies.

**Observations:**

- `Agents' Last Exam` had an outdated author list and submission status.
- `FICO` was listed as Findings of ACL on the website, while the TeX says ACL 2026.
- The multimodal evaluation survey was marked as a preprint on the website, while the TeX says under review at ARR.
- `resume.json` still included an Experience section that is absent from the updated TeX.
- `resume.json` was missing the Amazon Nova AI Challenge Grant and had stale AgentBeats project details.

**Outcome:** Patched the structured CV and bibliography to match the updated TeX. Verified with JSON validation and a full Docker/Jekyll build.
