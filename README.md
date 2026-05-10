# AI Ethics Alignment Quiz
 
> Discover which contemporary AI ethics frameworks best reflect your beliefs — and walk away with a personalized AI Ethics Bot skill file.
 
---
 
## What It Is
 
A self-contained, single-file web application that maps a student's or professional's beliefs about AI governance, risk, rights, and deployment onto ten contemporary ethical frameworks — from AI Alignment Theory to AI Abolitionism. No backend. No database. No build step. Drop the file anywhere and it works.
 
The quiz is designed for courses in AI ethics, technology policy, and responsible AI, but is accessible to anyone with an interest in where they stand on the most consequential technology debate of our time.
 
---
 
## Live Demo
 
Deploy `index.html` to any static host (GitHub Pages, Vercel, Netlify) and it's immediately live.
 
---
 
## Features
 
- **20 core questions** across 6 topic groups, with optional deep-dive expansions per topic
- **Importance weighting** — students rate how central each topic is to their thinking (Less / Somewhat / A lot), influencing their final scores
- **Go Deeper** — after each topic group, students can choose to answer additional nuanced questions for a more precise result
- **10 contemporary frameworks** scored simultaneously, each with classical philosophical roots
- **iSideWith-style results** — ranked list showing % alignment per framework, the 3 specific answers that drove each score, key thinkers, and classical lineage
- **PDF download** — full ranked results report, printable and shareable
- **Markdown skill file download** — a fully configured AI Ethics Bot instruction set the student pastes into any AI assistant to create their personalized ethics tutor
---
 
## The Ten Frameworks
 
| Framework | Key Thinkers | Classical Root |
|-----------|-------------|----------------|
| AI Alignment Theory | Russell, Yudkowsky | Deontology + Virtue Ethics |
| Existential Risk Ethics | Bostrom, Ord, Tegmark | Longtermism + Ethics of Responsibility |
| Effective Altruism | Singer, MacAskill | Utilitarianism |
| Transhumanism | Bostrom, Kurzweil, More | Capability Approach + Utilitarianism |
| Machine Ethics | Wallach, Allen | Virtue Ethics + Deontology |
| AI Governance & Accountability | Crawford, Floridi, Zuboff | Rawlsian Justice + Social Contract |
| Care-Based AI Ethics | Noddings, Eubanks, Benjamin | Care Ethics + Capability Approach |
| Techno-Pragmatism | Floridi, Jobin, Danaher | Pragmatism |
| Precautionary Ethics | Jonas, Weber, Habermas | Ethics of Responsibility |
| AI Abolitionism | Gebru, Noble, Benjamin | Critical Theory + Care Ethics |
 
---
 
## The Topic Groups
 
Questions are organized into six thematic areas, each with core questions and an optional deep-dive:
 
1. **AI Governance & Policy** — Who should govern AI, and how?
2. **Risk, Safety & Deployment** — What counts as an acceptable risk?
3. **Moral Frameworks & Duty** — How should we reason about AI ethics?
4. **AI Rights & Personhood** — Can machines have rights? Should they?
5. **Democracy, Power & Expertise** — Who benefits, and who decides?
6. **Data, Opacity & Accountability** — What do we owe the people AI affects?
---
 
## The Deliverables
 
After completing the quiz, students receive:
 
### Framework Rankings
A ranked list of all 10 frameworks with percentage match scores, key thinkers, classical lineage, and the specific answers that drove each score — making the results legible and pedagogically useful, not just a number.
 
### PDF Report
A downloadable summary of the full ranking, suitable for submission, reflection journals, or portfolio documentation.
 
### Markdown Skill File (`.md`)
A fully structured AI Ethics Bot instruction file containing:
- YAML frontmatter for skill routing
- The student's primary alignment and description
- Their full ranked framework table
- The answers that drove their top score
- Mission, persona, all 10 frameworks with thinkers
- A 5-step protocol for analyzing ethical dilemmas
- Behavioral rules for the bot
Paste into any AI assistant (Claude Project, custom GPT, etc.) to create a personalized ethics tutor grounded in the student's own worldview.
 
---
 
## Deployment
 
### GitHub Pages
1. Fork or clone this repository
2. Ensure `index.html` is in the root
3. Go to **Settings → Pages → Source: main branch / root**
4. Your quiz is live at `https://yourusername.github.io/repo-name`
### Vercel
1. Connect your GitHub repo to Vercel
2. No build configuration needed — Vercel serves `index.html` automatically
### Netlify
Drag and drop `index.html` onto [netlify.com/drop](https://netlify.com/drop). Done.
 
### Self-hosted / LMS
Copy `index.html` to any web server or embed in a Canvas page as an external tool URL. Everything — fonts (via Google Fonts CDN), images, logic — is self-contained or CDN-linked.
 
> **Note:** Google Fonts requires an internet connection. Everything else works fully offline.
 
---
 
## Technical Notes
 
### Architecture
```
index.html
├── <style>        CSS — layout, typography, animations, dark download bar
├── #heroScreen    Landing page — photo left, instructional copy right
├── #quizWrapper   20-question quiz with topic banners and Go Deeper prompts
├── #resultsScreen Framework rankings, score badges, answers tab
└── <script>       Question bank, scoring matrix, PDF generator, Markdown generator
```
 
### Scoring
Each question maps weights to each of the 10 frameworks. Responses are scored ±2/±1/0/-1/-2, multiplied by the importance weight (1–3). Percentage match = `(raw + max) / (2 × max) × 100`, producing a 0–100% alignment score per framework.
 
### Modifying Questions
Questions live in the `TOPICS` array in `<script>`. Each question has:
```javascript
{
  q: "Statement text.",
  ctx: "Optional context shown below the statement.",
  weights: { f1: 2, f6: 1, f9: -1, f4: -2 }  // framework IDs and weights
}
```
 
### Modifying Frameworks
Frameworks are defined in the `FRAMEWORKS` array. Each has an `id`, `name`, `color`, `thinkers`, `lineage`, and `desc`.
 
---
 
## Dependencies
 
| Library | Version | Purpose |
|---------|---------|---------|
| [jsPDF](https://github.com/parallax/jsPDF) | 2.5.1 | Client-side PDF generation |
| [IBM Plex Sans + Mono](https://fonts.google.com/specimen/IBM+Plex+Sans) | Google Fonts | Body and monospace typography |
| [Playfair Display](https://fonts.google.com/specimen/Playfair+Display) | Google Fonts | Display and heading typography |
 
No npm. No bundler. No framework.
 
---
 
## Pedagogical Notes
 
This quiz is designed to surface the **live debate** in contemporary AI ethics — not to map students back onto Kant or Mill. The ten frameworks represent positions actively held and contested by researchers, technologists, and critics right now.
 
The **Go Deeper** mechanic is intentional: it rewards students who want to engage more thoroughly with a topic, and produces more precise scores without burdening students who just want the overview.
 
The **AI Abolitionism** framework is included deliberately. The argument that "ethical AI" functions as a legitimizing fiction is a serious academic position with substantial literature. Excluding it would misrepresent the actual debate.
 
---
 
## License
 
MIT — use freely, adapt for your course, remix for your context.
 
---
 
*Built for AI ethics education. No data is collected. Everything runs locally in the browser.*
