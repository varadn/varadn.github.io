# Conference Portfolio Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Build and publish a single-page research portfolio that lets conference attendees understand Varad Nevasekar's work and contact him quickly.

**Architecture:** A dependency-free static GitHub Pages site will keep the page fast, portable, and easy to maintain. Semantic HTML owns the content and links; one CSS file owns the research-notebook visual system and responsive layout; the supplied resume PDF is copied as a downloadable asset.

**Tech Stack:** HTML5, CSS, GitHub Pages, browser-native behavior

**Spec:** `docs/superpowers/specs/2026-09-25-conference-portfolio-design.md`

## Global Constraints

- All factual claims must trace to the supplied resume.
- Public contact details are limited to `varad_nevasekar@student.uml.edu` and `linkedin.com/in/varad-nevasekar`.
- Do not include a phone number, contact form, blog, analytics, headshot, invented metrics, or new dependency.
- Keep body text at least 16px with visible keyboard focus and a logical heading outline.
- Support desktop and mobile without clipping or horizontal scrolling.

## Review Focus

- A narrow 320px viewport must remain readable without horizontal scrolling; verify in Task 2.
- A visitor using only a keyboard must reach every link and see focus; verify in Task 2.
- Every local asset reference must resolve, especially the resume download; verify in Task 1.
- External links must point to the intended email, LinkedIn profile, and DOI; verify in Task 1.
- The phone number must not appear in public site files; verify in Tasks 1 and 2.

---

### Task 1: Build the conference portfolio

**Files:**
- Create: `index.html`
- Create: `styles.css`
- Create: `assets/Varad-Nevasekar-Resume.pdf`

**Interfaces:**
- Consumes: factual content and constraints from the approved spec and source resume
- Produces: a self-contained static page at `/index.html`, styling at `/styles.css`, and a downloadable resume at `/assets/Varad-Nevasekar-Resume.pdf`

- [ ] **Step 1: Add the public resume asset**

Copy `/Users/varad/Documents/School/2026 summer/_Varad Nevasekar_UML_2026.pdf` to `assets/Varad-Nevasekar-Resume.pdf`; do not alter the source file.

- [ ] **Step 2: Verify the page does not exist yet**

Run: `test ! -f index.html`

Expected: exit status 0.

- [ ] **Step 3: Create the semantic page in `index.html`**

Include the introduction, the three featured projects, experience, IEEE publication and DOI, education and honors, selected skills, final contact invitation, email, LinkedIn, and resume download. Add basic title, description, viewport metadata, a skip link, logical headings, and safe external-link attributes.

- [ ] **Step 4: Create the visual system in `styles.css`**

Implement the approved deep-navy, white, and cyan research-notebook direction; a compact sticky navigation; a numbered project index; responsive desktop/mobile layouts; visible focus styles; readable typography; and reduced-motion support. Use CSS only for presentation and interaction states.

- [ ] **Step 5: Run static content checks**

Run:

```bash
test -f index.html && test -f styles.css && test -f assets/Varad-Nevasekar-Resume.pdf
rg -q 'mailto:varad_nevasekar@student\.uml\.edu' index.html
rg -q 'linkedin\.com/in/varad-nevasekar' index.html
rg -q 'doi\.org/10\.1109/UR65550\.2025\.11078138' index.html
! rg -n '510|396-5170' index.html styles.css
```

Expected: exit status 0 with no phone-number matches.

- [ ] **Step 6: Commit the page**

```bash
git add index.html styles.css assets/Varad-Nevasekar-Resume.pdf
git commit -m "feat: build conference research portfolio"
```

### Task 2: Verify and publish the site

**Files:**
- Modify: `index.html` only if browser verification reveals a content or accessibility defect
- Modify: `styles.css` only if browser verification reveals a layout, contrast, focus, or responsive defect

**Interfaces:**
- Consumes: the static site produced by Task 1
- Produces: a visually verified GitHub Pages site ready for conference visitors

- [ ] **Step 1: Serve the site locally**

Run: `python3 -m http.server 4173`

Expected: the page loads successfully at `http://127.0.0.1:4173/`.

- [ ] **Step 2: Inspect desktop and mobile layouts**

Check at approximately 1440x900, 768x1024, and 320x700. Confirm no clipping or horizontal scrolling, the first viewport communicates identity and research focus, and all sections remain legible.

- [ ] **Step 3: Verify keyboard and links**

Use Tab from the address bar through every page action. Confirm the skip link works, focus is always visible, and the email, LinkedIn, DOI, and resume links have correct destinations.

- [ ] **Step 4: Fix only defects found in Steps 2-3**

Keep changes within `index.html` and `styles.css`; do not add features or dependencies.

- [ ] **Step 5: Run final checks**

Run:

```bash
git diff --check
! rg -n '510|396-5170' index.html styles.css
test -s assets/Varad-Nevasekar-Resume.pdf
```

Expected: exit status 0, no whitespace errors, no phone-number matches, and a non-empty resume asset.

- [ ] **Step 6: Commit verified fixes if any**

```bash
git add index.html styles.css
git diff --cached --quiet || git commit -m "fix: polish portfolio presentation"
```

- [ ] **Step 7: Publish through the repository's GitHub Pages flow**

Push the completed `main` branch to its configured remote, then verify the public page and its resume download return successfully.

