# Conference Portfolio Design

## Goal

Create a public, mobile-friendly personal website that helps conference attendees quickly understand Varad Nevasekar's research, identify useful conversation topics, and connect afterward.

The resume is source material only. The site will not reproduce document instructions or publish Varad's phone number.

## Audience and Success Criteria

The primary audience is researchers, engineers, collaborators, and recruiters encountered at technical conferences. The page succeeds when a visitor can, within a short scan:

- understand Varad's focus across AI-enabled inspection, vision-language systems, robotics, and human-in-the-loop decision support;
- recognize the three featured research projects and Varad's contribution to each;
- open the IEEE publication or download the resume; and
- contact Varad through email or LinkedIn.

## Experience

The site is a single narrative page with a compact sticky navigation bar. The first viewport introduces Varad, states his research focus, and exposes the primary contact links without requiring scrolling.

Content order:

1. Introduction and contact actions
2. Featured research: Weld-PICA, CROSS-VLR, and Seeing Eye Stretch
3. Current and prior experience
4. IEEE Ubiquitous Robots publication
5. Education, honors, and selected technical skills
6. Closing contact invitation

The public actions are email, LinkedIn, DOI, and resume download. The site will not include a phone number, contact form, blog, analytics, headshot, or invented project metrics.

## Visual Direction

The page will resemble a polished research field notebook rather than an online resume template: deep navy surfaces, crisp white text, bright cyan accents, restrained grid lines, large editorial headings, and compact technical labels. The layout will use typography and spacing instead of decorative stock imagery.

A numbered project index and subtle connecting rule will make the research section memorable while staying readable. Motion, if used, will be limited to native hover and focus transitions and will respect reduced-motion preferences.

## Implementation

Use a small static GitHub Pages site built from semantic HTML and CSS, with JavaScript only if an interaction cannot be handled natively. Reuse the existing repository and add no dependencies unless the current platform requires them.

Expected files are the page, its stylesheet, and a public copy of the supplied resume PDF. Basic document metadata will support search and link previews. External links will use safe new-tab behavior where appropriate.

The layout will adapt from a two-column desktop composition to a single-column mobile flow without horizontal scrolling. Body text will remain at least 16px, interactive elements will have visible keyboard focus, headings will form a logical outline, and contrast will remain legible.

## Content Rules

All claims must trace to the supplied resume. Project descriptions may be tightened for scanning but may not add outcomes, collaborators, technologies, or measurements absent from the source.

The page will include:

- Draper Scholar, September 2025-present
- University of Massachusetts Lowell robotics research experience, December 2023-December 2024
- CarGurus software engineering co-op, July 2022-December 2022
- IEEE Ubiquitous Robots 2025 publication with DOI 10.1109/UR65550.2025.11078138
- Ph.D. expected May 2029, M.S. December 2024, and B.S. December 2023 from UMass Lowell
- selected honors and skills from the resume

Public contact details are limited to `varad_nevasekar@student.uml.edu` and `linkedin.com/in/varad-nevasekar`.

## Verification

Before delivery:

- render and inspect the page at desktop and mobile widths;
- confirm there is no clipping or unintended horizontal scrolling;
- navigate all interactive elements by keyboard and verify visible focus;
- verify email, LinkedIn, DOI, and resume-download links;
- confirm the phone number does not appear in site files; and
- run the repository's appropriate production check or static-file validation.

