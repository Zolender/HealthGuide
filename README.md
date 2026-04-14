# 🩺 HealthGuide — Browser-Based Symptom Checker

> A privacy-first, bilingual (English & Kinyarwanda) symptom checker that guides users through a structured triage process and delivers one of three clear health recommendations — entirely in the browser, with zero data storage.

![Made with HTML](https://img.shields.io/badge/Made%20with-HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![Styled with Tailwind](https://img.shields.io/badge/Styled%20with-TailwindCSS-38BDF8?style=flat-square&logo=tailwindcss&logoColor=white)
![Vanilla JS](https://img.shields.io/badge/Logic-Vanilla%20JS-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Privacy First](https://img.shields.io/badge/Privacy-100%25%20Browser--only-10B981?style=flat-square)
![Languages](https://img.shields.io/badge/Languages-English%20%7C%20Kinyarwanda-6366F1?style=flat-square)

---

## 📌 Overview

**HealthGuide** is a single-file web application built as a university practicum project. It simulates a basic medical triage experience — helping users assess their symptoms and decide whether to seek urgent care, rest and monitor, or self-manage at home.

It is **not a diagnostic tool**. It is a guided decision-support interface built on general triage principles.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🚨 Red Flag Detection | First question immediately flags life-threatening symptoms and routes to urgent care |
| 📋 8-Step Symptom Checker | Guided questions covering symptom type, duration, severity, fever, functionality, risk group, and progression |
| 🧠 Scoring Engine | Each answer contributes to an urgency score; thresholds determine the final recommendation |
| 🌍 Bilingual Support | Full English and Kinyarwanda translations including all questions, options, and UI text |
| 🌙 Dark / Light Theme | Toggle between themes with smooth transitions |
| 📊 Visual Feedback | Progress bar, step dots, urgency score bar, and animated result card |
| 💊 Self-Care Steps | Actionable home-care instructions shown for non-urgent outcomes |
| ⚠️ Limitations Disclosure | Clearly displayed on the landing page — this is a guide, not a diagnosis |
| 🔒 Privacy by Design | No data collected, stored, or transmitted. Runs 100% in the browser |
| 📱 Fully Responsive | Works on mobile, tablet, and desktop |

---

## 🖥️ Pages / Views

The app is a **single HTML file** with three JavaScript-rendered views:

### 1. 🏠 Landing Page
- App introduction and tagline
- "How it works" section (3 steps)
- **Limitations disclaimer** (required by design)
- Call-to-action to start the symptom check

### 2. 📋 Symptom Checker
- Step-by-step questions with smooth slide animations
- Progress bar and step indicator dots
- Back navigation support
- Slider input for pain severity (Question 4)

### 3. 💡 Results Page
- Colour-coded recommendation card (🔴 Urgent / 🟡 Monitor / 🟢 Self-manage)
- Urgency score visualisation
- Tailored self-care steps for non-urgent outcomes
- Disclaimer reminder
- Options to retake or return home

---

## 🧠 Decision Logic

The checker uses a **cumulative urgency scoring system**:

```
Question 1 — Red Flag       → YES: immediate urgent result (score bypassed)
Question 2 — Primary Symptom → 0–1 points
Question 3 — Duration        → 0–3 points
Question 4 — Severity (1–10) → 0–3 points
Question 5 — Fever           → 0–2 points
Question 6 — Functionality   → 0–3 points
Question 7 — Risk Group      → 0–2 points
Question 8 — Progression     → 0–3 points
                              ─────────────
                  Max Score:    ~14 points
```

### Score Thresholds

| Score | Recommendation |
|---|---|
| 0 – 3 | ✅ Self-Manage at Home |
| 4 – 7 | ⚠️ Rest and Monitor |
| 8+ | 🚨 Visit Clinic Urgently |

---

## 🌍 Language Support

All content — questions, answer options, UI labels, results, self-care steps, and disclaimers — is available in:

- 🇬🇧 **English**
- 🇷🇼 **Kinyarwanda**

Language is toggled via the `EN / RW` button in the navigation bar. The entire interface re-renders instantly with no page reload.

Translations are stored in a single `T` object in the JavaScript, following a clean i18n (internationalisation) pattern.

---

## 🗂️ Project Structure

```
healthguide/
└── index.html        ← Entire application (HTML + CSS + JS in one file)
└── README.md         ← This file
```

No build tools. No frameworks. No dependencies beyond:
- [Tailwind CSS CDN](https://tailwindcss.com) — utility-first styling
- [Google Fonts CDN](https://fonts.google.com) — typography (Inter, Playfair Display, Poppins, Lato)

---

## 🚀 Getting Started

### Option 1 — Open Locally
```bash
# No installation needed — just open the file
open index.html
# or double-click it in your file explorer
```

### Option 2 — Host on GitHub Pages
```bash
# 1. Create a new GitHub repository
# 2. Upload index.html and README.md
# 3. Go to Settings → Pages → Branch: main → Save
# 4. Your app will be live at:
https://yourusername.github.io/your-repo-name
```

### Option 3 — Deploy on Vercel
```bash
# 1. Go to vercel.com and sign in with GitHub
# 2. Import your repository
# 3. Click Deploy — done in under 60 seconds
```

---

## ⚠️ Limitations & Disclaimer

> **This tool is not a medical diagnostic system.**

- It does not replace consultation with a qualified healthcare professional
- Recommendations are based on general triage principles, not individual medical history
- It does not account for all possible conditions, drug interactions, or clinical nuances
- In any medical emergency, contact your local emergency services immediately
- The Kinyarwanda translations are provided for accessibility and should be reviewed by a qualified native-speaking health professional before clinical use

---

## 🎓 Academic Context

This project was developed as a **university practicum exercise** to demonstrate:

- Client-side application logic (decision trees in JavaScript)
- Accessible and inclusive UI/UX design principles
- Privacy-by-design implementation (no backend, no data storage)
- Multilingual interface development (i18n pattern)
- Evidence-informed software design using triage literature

---

## 🔗 Related Work & References

> *(To be completed in the accompanying academic report)*

Relevant literature and systems this project draws inspiration from:

- NHS 111 Online Symptom Checker — [https://111.nhs.uk](https://111.nhs.uk)
- WHO Integrated Management of Childhood Illness (IMCI) guidelines
- INESSS Clinical Decision Support frameworks
- Ada Health symptom checker — [https://ada.com](https://ada.com)
- Babylon Health triage logic research

---

## 👨‍💻 Built With

- **HTML5** — semantic structure
- **Tailwind CSS** (CDN) — utility-first responsive styling
- **Vanilla JavaScript** — decision tree engine, i18n, state management
- **Google Fonts** — Inter, Playfair Display, Poppins, Lato

---

## 📄 License

This project is open for educational use. No commercial licence is implied or granted.

---

<div align="center">
  <p>Built with ❤️ for learning · Powered by care, not servers</p>
  <p><strong>HealthGuide</strong> — Ubuzima bwawe ni ingenzi 🇷🇼</p>
</div>
