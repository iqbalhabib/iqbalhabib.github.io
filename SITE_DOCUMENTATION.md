# Iqbal Habib — Portfolio Website Documentation
**File:** `index.html` (4,961 lines)  
**Last Updated:** April 2026

---

## Table of Contents
1. [File Structure](#file-structure)
2. [Colors & Fonts](#colors--fonts)
3. [Navigation](#navigation)
4. [Hero Section](#hero-section)
5. [About Section](#about-section)
6. [Skills Section](#skills-section)
7. [Research Section](#research-section)
8. [Projects Section](#projects-section)
9. [Active Work Section](#active-work-section)
10. [Teaching Section](#teaching-section)
11. [Contact Section](#contact-section)
12. [Footer](#footer)
13. [Features & Settings](#features--settings)
14. [How to Edit Common Things](#how-to-edit-common-things)

---

## File Structure

Everything is in one file: `index.html`. Assets are in the `uploads/` folder.

```
my website (3)/
├── index.html              ← The entire website (HTML + CSS + JavaScript)
└── uploads/
    ├── LOGO.png            ← Site logo (top-left of nav)
    ├── IMG-20220203-WA0003.jpg  ← Profile photo (hero section)
    └── CV_Iqbal_Habib.pdf  ← CV download file
```

### Page Sections (in order)
| Section ID | Heading | Description |
|---|---|---|
| `#hero` | — | Landing section with photo, name, bio, stats |
| `#about` | Who I Am | Bio, timeline, achievement cards |
| `#skills` | Technical Expertise | Skill cards by domain |
| `#research` | Research & Publications | 7 peer-reviewed papers |
| `#projects` | Projects | 6 project showcase cards |
| `#active` | Active Work | Live progress on ongoing work |
| `#teaching` | Teaching | O/A Level tutoring info |
| `#contact` | Contact | Contact links + form |

---

## Colors & Fonts

### Change the Accent Color
Search for `--blue: #1a5eff` (around line 51) and change `#1a5eff` to any color you want.

### Full Color Palette (Light Mode)
```css
--w: #f9f8f5        /* page background (warm off-white) */
--w2: #ffffff       /* cards and sections background (white) */
--w3: #f2f0ea       /* subtle accent backgrounds */
--dark: #13110e     /* primary text (near black) */
--dark2: #2c2720    /* secondary text */
--dark3: #5a5248    /* muted/caption text */
--blue: #1a5eff     /* PRIMARY ACCENT — buttons, links, highlights */
--green: #00b87a    /* success / available badge */
--gold: #c9a84c     /* warm highlights */
--orange: #ff6b2b   /* alert / emphasis */
--border: #e5e0d6   /* light borders */
--border2: #cdc6ba  /* darker borders */
```

### Fonts (loaded from Google Fonts)
| Font | Used For |
|---|---|
| **Fraunces** | Section headings, hero name, logo text |
| **Plus Jakarta Sans** | Body text, paragraphs, nav links |
| **JetBrains Mono** | Badge labels, code-style text, stats labels |

### Icons
All icons come from **Lucide Icons** (version 0.469.0). To use a different icon, replace the icon name inside `data-lucide="..."`. Browse available icons at [lucide.dev/icons](https://lucide.dev/icons).

---

## Navigation

### Top Nav Links
The `<ul class="nav-links">` block (around line 2999):
```html
<li><a href="#about">About</a></li>
<li><a href="#skills">Skills</a></li>
<li><a href="#research">Research</a></li>
<li><a href="#projects">Projects</a></li>
<li><a href="#teaching">Teaching</a></li>
<li><a href="#contact">Contact</a></li>
<li><a href="mailto:mr.iqbalhabib@gmail.com" class="nav-hire">Hire Me</a></li>
```
To add a new section link: add another `<li><a href="#sectionid">Label</a></li>`.

### Hire Me Button Email
Change `mr.iqbalhabib@gmail.com` in the nav-hire link.

---

## Hero Section

### Profile Photo
```html
<img src="uploads/IMG-20220203-WA0003.jpg" ...>
```
Replace the filename to use a different photo. Keep it in `uploads/`.

### Availability Badge
```html
<span class="hv-avail">Open to Remote Roles & PhD Opportunities</span>
```
Change the text or remove the badge entirely.

### Stats (Publications, Teaching, CGPA)
Look for the `hstat` divs (around line 3080–3100):
```html
<div class="hstat">
  <span class="hstat-n" data-target="7">0</span>
  <span class="hstat-l">Publications</span>
</div>
<div class="hstat">
  <span class="hstat-n" data-target="5">0</span>
  <span class="hstat-l">Years Teaching</span>
</div>
<div class="hstat">
  <span class="hstat-n" data-target="3.92">0</span>
  <span class="hstat-l">Masters CGPA</span>
</div>
```
Change `data-target="7"` to update the number. Change the label text freely.

### Hero Bio / Summary Text
The paragraph near the CTA buttons (around line 3066):
```
Building AI/ML systems & data-driven solutions · IEEE-published Healthcare AI researcher ...
```
Edit directly.

### Typing Animation Roles
Look for the `typedRoles` array in the JavaScript (search `typedRoles`):
```js
const typedRoles = [
  'AI Researcher',
  'ML Engineer',
  'Statistical Modeller',
  'Healthcare AI Specialist',
  'O/A Level Educator',
  'Deep Learning Developer',
];
```
Add, remove, or edit the role strings.

### CV Download Button
```html
<a href="uploads/CV_Iqbal_Habib.pdf" ...>Download CV</a>
```
Replace the filename when you update your CV. Keep the new file in `uploads/`.

### Hero Role Cards (4 rows in the card)
Each row has an icon and 2 lines of text:
```html
<div class="hv-role">
  <div class="hv-icon"><i data-lucide="bot"></i></div>
  <div>
    <div class="hv-name">AI / ML Engineer</div>
    <div class="hv-sub">Deep Learning · Computer Vision · NLP · MLOps</div>
  </div>
</div>
```
Change the icon name, the bold title (`hv-name`), or the subtitle (`hv-sub`).

### Roles Ticker Strip (scrolling bar)
The strip that scrolls horizontally between hero and about (the `hero-marquee` div). Each tag:
```html
<span class="hm-tag t-blue"><i data-lucide="bot"></i> ML Engineer</span>
```
Color classes: `t-blue`, `t-green`, `t-orange`, `t-gold`, `t-purple`.

---

## About Section

### Bio Paragraphs
Three paragraphs inside `<div class="about-text rv-l">` (around line 3170–3178). Edit the text freely. Use `<strong>` for bold and `<em>` for italic.

### Achievement Cards (right column)
5 cards inside `<div class="about-cards">`. Each card:
```html
<div class="acard rv-r">
  <div class="acard-icon"><i data-lucide="graduation-cap"></i></div>
  <div class="acard-body">
    <div class="acard-title">MSc Applied Statistics & Data Science</div>
    <div class="acard-sub">3.92/4.00 CGPA · WES-evaluated 3.97/4.00 · Jahangirnagar University</div>
  </div>
</div>
```
Change the icon, title, and sub-text for each card.

### Timeline (Experience)
Each timeline item inside `<div class="timeline-wrap">`:
```html
<div class="tl-item tl-l rv">
  <div class="tl-year">Dec 2024 – Present</div>
  <div class="tl-dot"></div>
  <div class="tl-content">
    <div class="tl-title">Senior Research Associate</div>
    <div class="tl-org">Data Insightopia, Bangladesh</div>
  </div>
</div>
```
Change `tl-year`, `tl-title`, and `tl-org` for each entry. Items alternate left (`tl-l`) and right (`tl-r`).

**Current Timeline Entries:**
| Period | Role | Organization |
|---|---|---|
| Dec 2024 – Present | Senior Research Associate | Data Insightopia, Bangladesh |
| Nov 2023 – Present | Research Assistant | Pabna University of Science & Technology |
| Apr 2023 – Aug 2023 | Research Intern | AMIRL |
| 2022 – 2023 | MSc Applied Statistics & Data Science | Jahangirnagar University · CGPA 3.92/4.00 |
| 2020 – 2023 | Associate Data Analyst | Islam Jahid & Co., Bangladesh |
| 2013 – 2017 | BSc Mathematics | Govt. Edward College, Pabna |

---

## Skills Section

Six skill cards, each in a `<div class="skill-card rv">` block. Each card has:
- An icon (`data-lucide`)
- A title
- A list of skill tags

```html
<div class="skill-card rv">
  <div class="sk-icon"><i data-lucide="brain"></i></div>
  <div class="sk-title">Machine & Deep Learning</div>
  <div class="sk-tags">
    <span>PyTorch</span>
    <span>TensorFlow</span>
    <span>Keras</span>
    <!-- add more spans here -->
  </div>
</div>
```
To add a skill: add `<span>New Skill</span>` inside `sk-tags`.
To add a new card: copy an existing `skill-card` block and modify it.

**Current Skill Cards:**
1. Machine & Deep Learning — PyTorch, TensorFlow, Keras, Scikit-learn, CNNs, Transformers, RF, SVM, ANN
2. Healthcare AI & Imaging — Medical Imaging, Computer Vision, Image Processing, OpenCV, Grad-CAM, Histopathology
3. Statistics & Modelling — R, SPSS, MATLAB, PCA, Clustering, Regression, Survival Analysis, GLM
4. Data Science Tools — Python, Pandas, NumPy, SQL, Matplotlib, Seaborn, Plotly, Jupyter
5. Deployment & MLOps — Streamlit, FastAPI, Docker, GitHub, HuggingFace, Power BI, Tableau
6. Research & Writing — LaTeX, IEEE Format, Experimental Design, Literature Review, Statistical Reporting

---

## Research Section

### Adding / Editing a Paper
Each paper is a `<div class="paper rv">` block. Structure:

```html
<div class="paper rv">
  <div class="p-top">
    <span class="p-type conference">Conference Paper</span>  <!-- or "Journal" or "Under Review" -->
    <a href="https://doi.org/..." class="p-doi" target="_blank">DOI ↗</a>
  </div>
  <div class="p-venue">IEEE Venue Name · City, Year</div>
  <div class="p-title">Full Paper Title Here</div>
  <div class="p-authors"><strong>I. Habib</strong>, Co-Author Name</div>
  <div class="p-abstract">Conference/Journal citation info</div>
  <div class="p-tags">
    <span>Tag1</span>
    <span>Tag2</span>
  </div>
  <!-- Optional award badge: -->
  <div class="p-award"><i data-lucide="award"></i> Best Paper Award</div>
</div>
```

**Type badge classes:** `conference` (blue), `journal` (green), `review` (orange/gray).

### Current Papers (7)
| # | Title (short) | Venue | Status |
|---|---|---|---|
| 1 | Hybrid Xception-DenseNet121 for Leukemia | IEEE STI 2024 | Published |
| 2 | Hybrid DL for Blood Cancer Detection | IEEE ICRPSET 2024 | Published |
| 3 | EfficientNet for Leukemia Diagnosis | IEEE ICCIT 2024 | Published ⭐ Best Paper |
| 4 | ANN-LSTM & PINN for Stock Forecasting | Int. Journal of Computer Apps 2024 | Published |
| 5 | BNN-LSTM for Financial Forecasting | Int. Journal of Applied IS 2024 | Published |
| 6 | Women's Empowerment in Bangladesh | BMC Women's Health 2025 | Under Review |
| 7 | Medical Image Compression & Hybrid DL | Technologies 2026 | Under Review |

### Google Scholar Button
```html
<a href="https://scholar.google.com/citations?user=um-qnDkAAAAJ&hl=en" ...>
  View All Publications & Citations →
</a>
```
Update the URL if your Scholar profile link changes.

---

## Projects Section

### Adding / Editing a Project
Each project is a `<div class="proj-card rv">` block:

```html
<div class="proj-card rv" style="--bg1:#dbeaff;--bg2:#d0f5ea;">
  <div class="proj-img">
    <div class="proj-img-overlay"></div>
    <div class="proj-icon-big"><i data-lucide="search"></i></div>
  </div>
  <div class="proj-body">
    <div class="proj-top">
      <span class="proj-status published">Published</span>
    </div>
    <div class="proj-title">Project Title</div>
    <div class="proj-desc">Short description of the project...</div>
    <div class="proj-tech">
      <span>Python</span><span>Scikit-learn</span>
    </div>
    <a href="#" class="proj-link" target="_blank">View Thesis →</a>
  </div>
</div>
```

**Status badge classes:** `published` (blue), `in-progress` (orange), `completed` (green), `planning` (purple), `reviewing` (teal).

**Gradient colors:** Change `--bg1` and `--bg2` hex values for different card gradients.

### Current Projects (6)
| Project | Status | Link |
|---|---|---|
| Crime Analytics & Forecasting | Published | # (placeholder) |
| Cancer Detection — Hybrid DL | IEEE Published | # (placeholder) |
| Recommendation & Prediction Engine | In Progress | github.com/iqbalhabib |
| Biomedical Statistical Modelling | Completed | # (placeholder) |
| Clinical RAG Chatbot | Planning | github.com/iqbalhabib |
| Interactive Analytics Dashboard | Reviewing | # (placeholder) |

**To add a real link:** replace `href="#"` with the actual URL.

---

## Active Work Section

Three tabs: **Research**, **Projects**, **Teaching**. Each tab has progress items.

### Editing a Progress Item
```html
<div class="wcard rv">
  <div class="wcard-top">
    <div class="wicon wi-blue"><i data-lucide="dna"></i></div>
    <div class="wcard-meta">
      <div class="wname">Item Title Here</div>
      <div class="wsub">Subtitle / sub-description</div>
    </div>
    <span class="wbadge wb-blue">Building</span>
  </div>
  <div class="wdesc">Longer description of what you're working on...</div>
  <div class="prog-row" data-section="research">
    <div class="prog-label"><span>Progress</span><span class="prog-pct">45%</span></div>
    <div class="prog-bar"><div class="prog-fill" data-w="45"></div></div>
  </div>
  <div class="proj-tech">
    <span>Tag1</span><span>Tag2</span>
  </div>
</div>
```

**To update progress:** change both `45%` (display) and `data-w="45"` (animation) to the same number.

**Badge classes:** `wb-blue`, `wb-purple`, `wb-yellow`, `wb-green`.  
**Icon wrapper classes:** `wi-blue`, `wi-purple`, `wi-green`, `wi-orange`, `wi-gold`.

### Current Active Work
**Research tab:** Hybrid DL Extension (45%), LLM Literature Review (25%), PhD Application Prep (30%)  
**Projects tab:** Clinical RAG Chatbot (15%), Analytics Dashboard Migration (60%)  
**Teaching tab:** A Level Maths Cohort (70%), O Level Maths & Stats (85%)

---

## Teaching Section

### Intro Text
Find the `<div class="teaching-text">` block (around line 3760). Edit the paragraphs, years of experience, and subject descriptions.

### Booking / Facebook Buttons
```html
<a href="#contact" class="btn-main">Book a Session</a>
<a href="https://www.facebook.com/ihcambridgemath" class="btn-ghost" target="_blank">
  Facebook Page
</a>
```
Change the Facebook URL if needed.

### Subject Cards
Each subject is a `<div class="subj-card rv">` block:
```html
<div class="subj-card rv">
  <div class="sc-icon si-blue"><i data-lucide="ruler"></i></div>
  <div class="subj-name">Maths D & Additional Math</div>
  <div class="subj-lvl">O Level · A Level</div>
</div>
```

**Current Subjects:**
1. Maths D & Additional Math — O Level · A Level
2. Statistics — A Level
3. Mechanics — A Level
4. Further Math — A Level
5. Machine Learning — Introductory · Practical
6. Data Analysis — Applied · Python / R

**Icon color classes:** `si-blue`, `si-green`, `si-gold`, `si-orange`, `si-purple`.

### "Why Work With Me" Cards
Three cards (`.why-card`): **Exam-Focused**, **Concept-First**, **Flexible & Personalised**. Edit the title and description text directly.

---

## Contact Section

### Intro Text
Find the paragraph inside `<div class="csub rv">` and edit the text.

### Intent Badges (4 colored pills at the top)
```html
<div class="contact-badges">
  <span class="contact-badge-pill cb-blue">PhD Collaborations</span>
  <span class="contact-badge-pill cb-green">Remote AI/ML Roles</span>
  <span class="contact-badge-pill cb-gold">O/A Level Tutoring</span>
  <span class="contact-badge-pill cb-orange">Research Consulting</span>
</div>
```
Edit the text or add new pills.

### Contact Links
Each contact method is a `<a class="clink">` block:
```html
<a class="clink cl-blue" href="mailto:mr.iqbalhabib@gmail.com">
  <span class="clink-icon"><i data-lucide="mail"></i></span>
  <span class="clink-text">
    <span class="clink-label">Email</span>
    <span class="clink-val">mr.iqbalhabib@gmail.com</span>
  </span>
</a>
```
**To change email:** update both `href="mailto:..."` and the visible text.

**Current Contact Links:**
| Type | Value |
|---|---|
| Email | mr.iqbalhabib@gmail.com |
| Phone / WhatsApp | +880 1738 103211 |
| GitHub | github.com/iqbalhabib |
| LinkedIn | linkedin.com/in/mr-iqbal-habib |
| Google Scholar | scholar.google.com/citations?user=um-qnDkAAAAJ |
| Teaching (Facebook) | facebook.com/ihcambridgemath |
| CV Download | uploads/CV_Iqbal_Habib.pdf |

### Contact Form
The form uses **Web3Forms** to send emails without a backend.
- **Access Key:** `5fe4c7cb-c67f-4706-a17c-5af6ddbd8013`  
  (This key routes submissions to your email. Do not share it publicly.)
- **Form fields:** Name, Email, Subject (dropdown), Message
- **Subject dropdown options** — to add/remove options, find the `<select>` block and edit the `<option>` tags.

To change what email address receives messages, log into [web3forms.com](https://web3forms.com) with your account.

---

## Footer

```html
<p class="f-copy">
  © 2025 Iqbal Habib · AI/ML Engineer · Data Scientist · Researcher · Educator · Bangladesh
</p>
```
Update the year or text here. The footer also has icon links for Email, GitHub, LinkedIn, and Google Scholar — update the `href` values if they change.

---

## Features & Settings

### Dark / Light Mode
- Toggles via the moon/sun button in the top-right nav
- User preference is saved in `localStorage` under the key `ih-theme`
- Automatically picks system preference on first visit

### Scroll Progress Bar
The thin colored bar at the very top of the page that fills as you scroll. It's the `#scroll-progress` div. To hide it, add `display: none;` to its CSS rule.

### Side Dot Navigation (Desktop Only)
The dot menu on the right side of the screen (hidden on screens narrower than 1100px). It shows 8 section dots with labels. To add or remove a dot, edit the `<nav class="side-nav">` block near the bottom of the HTML body.

### Section Toast
A small label that pops up at the bottom center when you enter a new section. The labels are in the `SEC_LABELS` JavaScript object:
```js
const SEC_LABELS = {
  hero: 'Home', about: 'About', skills: 'Skills',
  research: 'Research', projects: 'Projects',
  active: 'Active Work', teaching: 'Teaching', contact: 'Contact'
};
```

### Scroll Behavior
- Scrolling is smooth by default (`scroll-behavior: smooth` on `html`)
- Sections don't have a scroll-margin, so the fixed nav (66px tall) may overlap slightly when navigating via anchor links

### Custom Cursor
The site uses a custom dot cursor (visible on desktop). Defined by the `#cur` and `#cur2` divs. To disable it, remove those divs from the HTML and remove the `cursor: none !important` CSS rules.

---

## How to Edit Common Things

### Update a stat number (e.g., publications went from 7 to 8)
1. Find `data-target="7"` in the hero section
2. Change to `data-target="8"`
3. The counter animation will show the new number

### Add a new publication
1. Find the research section (`<section id="research">`)
2. Copy an existing `<div class="paper rv">` block
3. Paste it and update: type badge, DOI link, venue, title, authors, abstract citation, and tags
4. Update the publication count stat in the hero section

### Update your CV
1. Add the new PDF to `uploads/` (e.g., `CV_Iqbal_Habib_2026.pdf`)
2. Find all references to `CV_Iqbal_Habib.pdf` (there are 2–3) using Ctrl+F
3. Replace the filename

### Change your profile photo
1. Add the new photo to `uploads/`
2. Find `IMG-20220203-WA0003.jpg` and replace with the new filename

### Add a new project
1. Find the projects section (`<section id="projects">`)
2. Copy an existing `<div class="proj-card rv">` block
3. Update the gradient colors (`--bg1`, `--bg2`), icon, status badge, title, description, tech tags, and link
4. The grid auto-arranges — no layout changes needed

### Change the accent color globally
1. Find `--blue: #1a5eff;` (around line 51)
2. Change the hex code to your new color
3. Also update the dark mode version `--blue: #5b82ff;` (around line 77)

### Add a new section
1. Add a `<section id="newsection">` with your content in the HTML body
2. Add a nav link: `<li><a href="#newsection">Label</a></li>`
3. Add a side dot: copy an existing `<div class="side-dot">` and update `data-section="newsection"` and the label
4. Add to the `SEC_LABELS` object in JavaScript

---

*This documentation covers the complete content and structure of the portfolio as of April 2026.*
