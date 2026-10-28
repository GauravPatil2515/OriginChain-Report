# OriginChain: Major Project Report (Semester 7)

**OriginChain: Blockchain-Based Quality Assurance, Authentication and Supply-Chain Traceability for Luxury Cosmetics**

Submitted in partial fulfilment of the requirements of the degree of  
**Bachelor of Computer Engineering**  
Department of Computer Engineering  
**A. P. Shah Institute of Technology, Thane** (University of Mumbai)  
Academic Year: **2026–2027**

---

## Project Team
- **Durva Waghchaure** (Roll No: 23102152) – *Backend & Project Lead*
- **Aryan Singh** (Roll No: 23102154) – *Blockchain Lead*
- **Purvika Thombare** (Roll No: 23102097) – *AI & Quality Lead*
- **Aradhya Thakur** (Roll No: 23102110) – *Frontend Lead*

**Project Guide:** Prof. Pranali Patil  
**Project Coordinator:** Dr. Rushikesh R. Nikam  
**Head of Department:** Dr. Sachin Malave  
**Principal:** Dr. Uttam Kolekar  

---

## Repository Contents

- `OriginChain_Report.tex` — Master LaTeX source code adhering strictly to the University of Mumbai / APSIT B.E. Major Project Report format.
- `OriginChain_Report.pdf` — Ready-to-print compiled PDF report (47 pages) with preliminary pages, chapters, figures, tables, and references.
- `output/OriginChain_Report_Formatted.pdf` — Production deliverable PDF matching all university formatting rubrics.
- `output/Formatting_Audit.md` — Complete page-by-page quality audit documenting visual and programmatic verifications.
- `images/` — High-resolution architectural, UML, sequence, Gantt, and college insignia assets.
- `images/screenshots/` — Extracted UI screenshots covering authentication, quality board, certificate of authenticity, consumer verification, and admin log.

---

## How to Compile LaTeX Source

To compile the LaTeX source into a PDF:

```bash
pdflatex -interaction=nonstopmode OriginChain_Report.tex
pdflatex -interaction=nonstopmode OriginChain_Report.tex
```
*(Running twice ensures Table of Contents, List of Figures, List of Tables, and references resolve properly).*

---

## Report Outline & Structure

1. **Preliminary Pages (Roman Numerals: Pages i to x):**
   - Title / Cover Page (Unnumbered, matching APSIT layout)
   - Institute Certificate (Page ii)
   - Project Report Approval for B.E. (Page iii)
   - Academic Honesty Declaration (Page iv)
   - Abstract & Sustainable Development Goals (SDG 3, 9, 12, 16) Alignment (Page v)
   - Table of Contents (`CONTENTS`: Pages vi–vii)
   - List of Figures (`LIST OF FIGURES`: Page viii)
   - List of Tables (`LIST OF TABLES`: Page ix)
   - List of Abbreviations (`ABBREVIATION`: Page x)
2. **Main Body (Arabic Numerals: Pages 1 to 37):**
   - **Chapter 1:** Introduction (Background, Overview, Cosmetics Domain Context, Technology Stack, Significant Contributions)
   - **Chapter 2:** Literature Survey (Reviewed literature + comparative summary Table 2.1)
   - **Chapter 3:** Limitations of Existing System
   - **Chapter 4:** Problem Statement, Objectives and Scope
   - **Chapter 5:** Proposed System (Architecture, UML Diagrams, Algorithms, Backend Modules, Roles, Data Placement Matrix, Section 5.12 Implementation Screenshots)
   - **Chapter 6:** Experimental Setup (Input Data, Evaluation Parameters, Test Suite Distribution, Hardware/Software Specs)
   - **Chapter 7:** Project Plan (Gantt Chart & Team Responsibilities)
   - **Chapter 8:** Expected Outcome
   - **Chapter 9:** Projected Cost Analysis (Prototype vs Polygon Production)
   - **Chapter 10:** References (24 IEEE-formatted citations)

---

# Comprehensive Guide: How to Prompt an AI Agent to Build & Overhaul a LaTeX University Report

This section serves as an end-to-end blueprint explaining the exact prompt engineering workflow, iterative feedback loop, and programmatic verification methods required to produce an authentic, publication-grade academic report in LaTeX from a reference PDF or Word document.

---

### Step 1: Baseline Structural Extraction & Template Ingestion

When replicating an official university format from an existing reference PDF (e.g., `Major PROject report sem 7.pdf`), do **not** ask the model to "make a project report" generically. Instead, direct it to extract the geometry, font hierarchy, and structural sequence.

**Effective Prompt:**
> *"Analyze `reference_report.pdf` using PyMuPDF / pdftotext. Extract: (1) Total page count and margin geometry, (2) Typography breakdown per block (font family, exact pt size, bold/italic flags), (3) Exact sequence of preliminary front-matter pages (Title, Certificate, Approval, Declaration, Abstract, Contents, List of Figures/Tables, Abbreviations), (4) Chapter numbering and heading styles. Replicate this exact academic format into a single self-contained LaTeX document `Project_Report.tex`."*

---

### Step 2: Strict Layout, Geometry, and Font Constraints

Academic university boards have strict margins for physical binding (1.5 inches on the left) and standard 1.0-inch margins on all other sides, along with 1.5 line spacing.

**Effective Prompt:**
> *"Use LaTeX standard `report` class with `[12pt, a4paper]`. Set geometry via `\usepackage[left=1.5in, right=1.0in, top=1.0in, bottom=1.0in]{geometry}` and `\usepackage{setspace}\onehalfspacing`. Use `mathptmx` for genuine Times New Roman typography. Ensure chapter titles are centered, capitalized, and set to 14–15pt bold with 16pt line spacing, section titles to 13pt bold, and subsection titles to 12pt bold."*

---

### Step 3: Two-Tier Numbering & Table of Contents Synchronization

University standards mandate lower-case Roman numerals (`i`, `ii`, `iii`...) for front matter and standard Arabic numerals (`1`, `2`, `3`...) starting at Chapter 1.

**Effective Prompt:**
> *"Enforce a strict two-tier pagination system:  
> 1. Start front matter with `\pagenumbering{roman}\setcounter{page}{2}` on the Certificate page (leaving the Title page unnumbered).  
> 2. Right before `\chapter{Introduction}`, insert `\cleardoublepage\pagenumbering{arabic}\setcounter{page}{1}` so Chapter 1 starts on Page 1.  
> 3. Ensure the Table of Contents (`\tableofcontents`), List of Figures (`\listoffigures`), and List of Tables (`\listoftables`) reflect these Arabic page numbers accurately by running two consecutive compilation passes."*

---

### Step 4: Extracting and Embedding Software UI Screenshots

Project reports require dedicated implementation screenshots showcasing key software capabilities.

**Effective Prompt:**
> *"Extract high-resolution raster screenshots from `Screenshots.pdf` into `images/screenshots/`. In Chapter 5 (Proposed System), add Section 5.12: 'Implementation Details (Screenshots)'. Embed each screenshot on a centered, dedicated figure block with `width=0.88\textwidth`, keepaspectratio, and descriptive academic captions:  
> - 5.12.1 Sign-in and Role Switching (Figure 5.8)  
> - 5.12.2 Supply-Chain Product & Batch Overview (Figure 5.9)  
> - 5.12.3 Quality Board & Check Enforcement (Figure 5.10)  
> - 5.12.4 Certificate of Authenticity (Figure 5.11)  
> - 5.12.5 Public Consumer Verification Portal (Figure 5.12)  
> - 5.12.6 Administrative Audit & Activity Log (Figure 5.13)"*

---

### Step 5: Side-by-Side Visual Verification & Pixel Matching

AI models cannot visually "see" a PDF unless they render the pages to images and inspect the bounding boxes and rendered layouts.

**Effective Prompt:**
> *"Render pages 1 to 10 of both the reference PDF and the newly generated report PDF at 150 DPI using PyMuPDF (`get_pixmap()`). Compare each page side-by-side:  
> - Verify college logo scaling and vertical centering on the Cover page.  
> - Ensure Certificate signature blocks have 4 distinct lines for ink signing.  
> - Check that the Declaration has right-aligned student signature lines with roll numbers.  
> - Check that the Abstract has zero indentation (`\setlength{\parindent}{0pt}`) on all paragraphs.  
> - Verify that the Abbreviation page is rendered as a clean bordered grid table."*

---

### Step 6: Automated Log Auditing for Zero TeX Overflows

Overfull horizontal boxes (`\hbox`) occur when monospace text (`\texttt`), URLs, table columns, or math formulas exceed page margins.

**Effective Prompt:**
> *"Compile the document with `pdflatex -interaction=nonstopmode` and parse the `.log` file for `Overfull \hbox` and `Underfull \hbox`.  
> - Wrap long monospace identifiers with `\allowbreak` or break across lines.  
> - Convert long inline equations to display math blocks (`\[ ... \]`).  
> - Replace fixed `p{...}` columns with flexible `tabularx` columns (`Y` or `L{...}`).  
> - Do not stop until the log reports **0 Overfull `\hbox`** and **0 Overfull `\vbox`** across the entire document."*

---

### Step 7: Structuring References as Chapter 10

Many LaTeX templates place references in an unnumbered bibliography. For Indian University project reports, References must often be numbered as the final chapter.

**Effective Prompt:**
> *"Redefine `thebibliography` so that References is designated as `\chapter{References}` (`Chapter 10`). Ensure all citations ([1] to [24]) are formatted in IEEE style with hanging indents and automatically indexed into the Table of Contents."*
