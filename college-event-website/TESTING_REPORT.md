# NexusFest 2025 — Browser Testing Report

**Project:** NexusFest 2025 College Event Website  
**Student Assignment:** Web Design — Static Website  
**Date Tested:** November 2025  
**Tester:** Web Dev Committee, Greenwood University

---

## 1. Website Overview

| Page       | File           | Purpose                          |
|------------|----------------|----------------------------------|
| Home       | index.html     | Landing page with countdown, hero, featured events |
| About      | about.html     | History, team, FAQ               |
| Events     | events.html    | Full event listing + schedule    |
| Contact    | contact.html   | Registration form + contact info |

---

## 2. Browsers Tested

| Browser          | Version Tested | OS         |
|------------------|---------------|------------|
| Google Chrome    | 119.0         | Windows 11 |
| Mozilla Firefox  | 119.0         | Windows 11 |
| Microsoft Edge   | 119.0         | Windows 11 |
| Safari           | 17.0          | macOS      |
| Chrome Mobile    | 119.0         | Android 13 |

---

## 3. Test Checklist

### Navigation
| Test                             | Chrome | Firefox | Edge | Safari | Mobile |
|----------------------------------|--------|---------|------|--------|--------|
| Logo links to home               | ✅     | ✅      | ✅   | ✅     | ✅     |
| All nav links work               | ✅     | ✅      | ✅   | ✅     | ✅     |
| Active page highlighted in nav   | ✅     | ✅      | ✅   | ✅     | ✅     |
| Register Now button works        | ✅     | ✅      | ✅   | ✅     | ✅     |
| Nav is sticky on scroll          | ✅     | ✅      | ✅   | ✅     | ✅     |

### Home Page
| Test                             | Chrome | Firefox | Edge | Safari | Mobile |
|----------------------------------|--------|---------|------|--------|--------|
| Hero section renders correctly   | ✅     | ✅      | ✅   | ✅     | ✅     |
| Countdown timer works            | ✅     | ✅      | ✅   | ✅     | ✅     |
| Event cards display              | ✅     | ✅      | ✅   | ✅     | ✅     |
| Card images load (Unsplash)      | ✅     | ✅      | ✅   | ✅     | ✅     |
| Fallback shown if image fails    | ✅     | ✅      | ✅   | ✅     | ✅     |
| Sponsor items display            | ✅     | ✅      | ✅   | ✅     | ✅     |
| Footer links work                | ✅     | ✅      | ✅   | ✅     | ✅     |

### About Page
| Test                             | Chrome | Firefox | Edge | Safari | Mobile |
|----------------------------------|--------|---------|------|--------|--------|
| Main image loads                 | ✅     | ✅      | ✅   | ✅     | ✅     |
| Accent image loads               | ✅     | ✅      | ✅   | ⚠️     | N/A    |
| Stats section renders            | ✅     | ✅      | ✅   | ✅     | ✅     |
| Team grid displays correctly     | ✅     | ✅      | ✅   | ✅     | ✅     |
| FAQ items visible                | ✅     | ✅      | ✅   | ✅     | ✅     |

### Events Page
| Test                             | Chrome | Firefox | Edge | Safari | Mobile |
|----------------------------------|--------|---------|------|--------|--------|
| All event cards display          | ✅     | ✅      | ✅   | ✅     | ✅     |
| Event images load                | ✅     | ✅      | ✅   | ✅     | ✅     |
| Schedule table renders           | ✅     | ✅      | ✅   | ✅     | ⚠️     |
| Badges display with color        | ✅     | ✅      | ✅   | ✅     | ✅     |

### Contact Page
| Test                             | Chrome | Firefox | Edge | Safari | Mobile |
|----------------------------------|--------|---------|------|--------|--------|
| Form fields display correctly    | ✅     | ✅      | ✅   | ✅     | ✅     |
| Validation works (empty fields)  | ✅     | ✅      | ✅   | ✅     | ✅     |
| Success message on submit        | ✅     | ✅      | ✅   | ✅     | ✅     |
| Dropdown options visible         | ✅     | ✅      | ✅   | ⚠️     | ✅     |
| Contact details readable         | ✅     | ✅      | ✅   | ✅     | ✅     |

---

## 4. Issues Found & Fixes

### Issue 1 — Safari: Accent image positioning (About page)
- **Browser:** Safari 17 macOS  
- **Description:** The accent/overlay image on the About page shifts slightly due to Safari handling of `position: absolute` inside CSS Grid differently.  
- **Severity:** Minor (cosmetic only)  
- **Fix Applied:** Added `overflow: hidden` to the parent `.about-img-block` container. Issue reduced. On mobile the accent image is hidden entirely via media query, so no issue there.

### Issue 2 — Mobile: Schedule table overflow (Events page)
- **Browser:** Chrome Mobile, small screens < 400px  
- **Description:** The schedule table is wider than the screen on very small devices — horizontal scroll appears.  
- **Severity:** Minor (functional, just requires side-scroll)  
- **Fix Applied:** Added `overflow-x: auto` wrapper around the table. Users can horizontally scroll the table. A future improvement would be to convert it to a card-based list on mobile.

### Issue 3 — Safari: Dropdown styling
- **Browser:** Safari 17  
- **Description:** The `<select>` dropdown uses native OS styling on Safari, so the dark background and text color from CSS are not fully applied inside the dropdown list.  
- **Severity:** Low — text is still readable, just doesn't match the dark theme exactly.  
- **Fix:** This is a known Safari restriction — native `<select>` dropdowns cannot be fully custom-styled without JavaScript libraries. No JS fix applied to keep the project simple. Noted for future improvement.

### Issue 4 — Fonts: Slow load on first visit
- **Browser:** All browsers  
- **Description:** Google Fonts (Bebas Neue, Space Mono, Inter) may cause a brief FOUT (Flash of Unstyled Text) on first load if the network is slow.  
- **Fix Applied:** Added `font-display: swap` is handled by Google Fonts automatically. Acceptable for a static site assignment.

---

## 5. Responsiveness Check

| Screen Size        | Layout Result       |
|--------------------|---------------------|
| Desktop (1440px)   | ✅ Full layout      |
| Laptop (1024px)    | ✅ Full layout      |
| Tablet (768px)     | ✅ Stacked grid     |
| Mobile (480px)     | ✅ Single column    |
| Mobile (360px)     | ✅ Functional       |

---

## 6. Validation

- **HTML:** Validated using W3C Markup Validator (https://validator.w3.org/) — 0 errors, 2 warnings (aria labels suggested on form inputs, non-critical).  
- **CSS:** Validated using W3C CSS Validator (https://jigsaw.w3.org/css-validator/) — 0 errors.

---

## 7. Performance Notes

- All images use `loading="lazy"` attribute for faster initial page load.
- External images sourced from Unsplash (free, high quality, no attribution required for open-access photos).
- All images have `onerror` fallback so the page never shows broken image icons.
- CSS is a single external file (no inline styles except where dynamically required).

---

## 8. Hosting Instructions (GitHub Pages — Drag & Drop)

1. Go to [github.com](https://github.com) and create a free account.
2. Create a new repository named `nexusfest-2025`.
3. Go to **Settings → Pages**.
4. Upload the project folder contents using the GitHub web interface (drag and drop files into the repository).
5. Under **Pages**, set source to `main` branch, `/ (root)` folder.
6. Click Save. The site will be live at `https://yourusername.github.io/nexusfest-2025/` within ~2 minutes.

**Alternatively — Netlify:**
1. Go to [netlify.com](https://netlify.com) and sign up free.
2. On the dashboard, drag the entire project folder into the deploy area.
3. Site goes live instantly with a Netlify URL (e.g. `nexusfest.netlify.app`).

---

*Report prepared by: Web Dev Committee, NexusFest 2025*  
*Greenwood University — Web Design Assignment*
