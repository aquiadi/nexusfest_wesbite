# NexusFest 2025 — College Event Website
### Web Design Assignment | Greenwood University

---

## Project Purpose
A static multi-page website for **NexusFest 2025**, the annual college cultural and technical festival. Built as part of the Web Design course assignment.

## Target Users
- Current college students looking to register for events
- Outstation participants checking event details and accommodation
- Faculty and sponsors looking to contact the organising committee

## Pages
| Page         | File           | Description                          |
|--------------|----------------|--------------------------------------|
| Home         | `index.html`   | Hero, countdown, featured events, sponsors |
| About        | `about.html`   | History, mission, team, FAQ          |
| Events       | `events.html`  | All events + full 3-day schedule     |
| Contact      | `contact.html` | Registration form + contact details  |

---

## Folder Structure

```
college-event-website/
│
├── index.html            ← Home page
├── about.html            ← About page
├── events.html           ← Events page
├── contact.html          ← Contact & Register page
│
├── css/
│   └── style.css         ← External stylesheet (all pages)
│
├── images/               ← Local images (if any downloaded)
│
├── assets/               ← Fonts, icons, other assets
│
├── TESTING_REPORT.md     ← Browser compatibility report
└── README.md             ← This file
```

---

## Technologies Used
- **HTML5** — Semantic elements (`<nav>`, `<section>`, `<article>`, `<footer>`, `<header>`)
- **CSS3** — Flexbox, Grid, CSS Variables, Media Queries, Transitions
- **Google Fonts** — Bebas Neue, Space Mono, Inter
- **JavaScript** — Countdown timer, form validation (vanilla JS, no libraries)
- **Unsplash** — Free open-access images (no attribution required)

## Features
- Responsive design (mobile, tablet, desktop)
- Live countdown timer to the event date
- Working registration form with validation
- Browser fallback for images (onerror attribute)
- Active page highlighted in navigation
- Schedule table with category badges

---

*Built by the Web Dev Committee — NexusFest 2025*
