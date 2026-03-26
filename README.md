# DS Tech — IT & Cybersecurity Services Website

<div align="center">

![DS Tech](https://img.shields.io/badge/DS%20Tech-IT%20%26%20Cybersecurity-7B2FFF?style=for-the-badge&logoColor=white)
![HTML](https://img.shields.io/badge/HTML5-Single%20File-E34F26?style=for-the-badge&logo=html5&logoColor=white)
![CSS](https://img.shields.io/badge/CSS3-Inline%20Styles-1572B6?style=for-the-badge&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-Vanilla%20JS-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)

**A fully custom, dark-mode IT & Cybersecurity services website built for DS Tech.**  
Built by Dasiah Silva — IT & Cybersecurity Specialist.

</div>

---

## ✨ Overview

DS Tech is a professional single-file website for an IT support and cybersecurity consulting business. It features a dark, futuristic design system in violet and cerulean, a multi-page single-page-application (SPA) structure, a client callback request form, a reviews system, and a password-protected admin dashboard — all in one self-contained `.html` file with zero dependencies except Google Fonts.

---

## 🎨 Design System

The site uses a custom CSS design language built around three core colors:

| Token | Hex | Usage |
|-------|-----|-------|
| **Violet** | `#7B2FFF` | Primary brand color, buttons, glows, borders |
| **Violet Light** | `#9B5FFF` | Gradients, hover states, logo text |
| **Cerulean** | `#00B4D8` | Accents, kickers, stat numbers, star ratings |
| **Background** | `#0A0A12` | Near-black page background |
| **Background Mid** | `#11111E` | Section & footer backgrounds |
| **Background Card** | `#14142A` | Card surfaces |
| **Ink** | `#E8E8FF` | Primary text |
| **Ink Soft** | `#A0A0C0` | Body / secondary text |

**Typography:**
- **Headings:** Space Grotesk (Google Fonts) — 700 weight
- **Body:** Inter (Google Fonts) — 400/500 weight

**Visual effects:**
- Animated gradient orbs in the hero background
- Rotating ring animations on the hero circle and about avatar
- Scrolling announcement ticker bar at the top
- Hover glows on cards, buttons, and interactive elements
- Subtle CSS grid overlay on the page background
- Page fade-in transitions

---

## 📄 Pages

The site is a single `.html` file structured as a multi-page SPA. Each "page" is a `<div>` that shows/hides via JavaScript — no page reloads, instant navigation.

### 🏠 Home
The main landing page with five sections:

| Section | Description |
|---------|-------------|
| **Hero** | Full-height hero with animated rings, laptop image, headline, and two CTA buttons |
| **Stats Band** | Four key metrics — 100+ Clients, 98% Satisfaction, 24h Response, 3+ Years |
| **Services Grid** | Six service cards with emoji icons |
| **Why Choose Me** | Six reason cards with numbered labels |
| **CTA Band** | Final call-to-action with a "Request a Callback" button |

### 👤 About
A two-column layout with:
- **Sidebar** — profile image with animated violet spinning ring, name, role title, two CTA buttons, and skill badges
- **Main content** — bio sections ("Hi, I'm Dasiah Silva", "My Approach", "Why DS Tech?") with a pull-quote

**Skill Badges:** Windows · Google Cybersecurity · Networking · Hardware · Upgrades

### 📞 Let's Connect
A callback request page with:
- **Left column** — contact info items (Phone Support, Remote Support, On-Site Service, Response Time)
- **Right column** — callback form (First Name + Phone Number) that saves to `localStorage` and displays a confirmation message

### ⭐ Testimonials
A grid of six client testimonials plus a **Leave a Review** section (see below).

**Featured clients:** Marcus R. · Jennifer L. · Tyler C. · Aisha K. · David P. · Sandra M.

### ⚙️ Dashboard *(Admin only)*
A password-protected admin panel for managing callback requests.

---

## 🔧 Services Offered

| Icon | Service | Description |
|------|---------|-------------|
| 🖥 | **Hardware Upgrades** | CPU, GPU, RAM, and storage installation & configuration |
| 🌐 | **Network Setup** | Infrastructure, security, cloud integration, automation |
| 🔒 | **Cybersecurity Consulting** | Vulnerability assessment, defense hardening |
| ⚙️ | **Installation** | OS installs, Google Workspace, Microsoft 365 |
| 💾 | **Backup Data** | Automated backup strategy design |
| 🦠 | **Virus & Malware Removal** | Full system cleaning with root-cause analysis |

---

## ⭐ Leave a Review System

Located at the bottom of the **Testimonials page**, this is a fully functional review submission and management system.

### Customer-Facing Form
- **Interactive star rating** — hover & click to rate 1–5 stars with animated cerulean glow
- **Name**, **Role** (optional), **Email**, and **Review text** fields
- Live character counter (up to 1,000 characters)
- Full client-side validation
- Reviews are saved to `localStorage` immediately on submission
- Optional **EmailJS integration** to send email notifications to the admin on each new review

### Admin Review Panel
Accessible via the small "⚙ Admin: View Submitted Reviews" link at the bottom of the section. Password-protected.

**Admin features:**
| Feature | Description |
|---------|-------------|
| View all reviews | Name, role, email, star rating, date/time, full text |
| Approve / Unapprove | Toggle approval status per review |
| Delete | Remove individual reviews |
| Export CSV | Download all reviews as a `.csv` spreadsheet |
| Clear All | Delete all reviews with confirmation |

### Setting Up Email Notifications (Optional — Free)
1. Sign up at [emailjs.com](https://emailjs.com) (free plan: 200 emails/month)
2. Create a Gmail (or other) email service
3. Create an email template using these variables:
   - `{{from_name}}` — reviewer's name
   - `{{from_email}}` — reviewer's email
   - `{{from_role}}` — reviewer's role/title
   - `{{star_rating}}` — e.g. "5 / 5 stars"
   - `{{review_text}}` — the review content
   - `{{submit_date}}` — submission date and time
4. In the HTML, find these three placeholders and replace with your real IDs:
```javascript
const EMAILJS_SERVICE_ID  = 'YOUR_SERVICE_ID';
const EMAILJS_TEMPLATE_ID = 'YOUR_TEMPLATE_ID';
const EMAILJS_PUBLIC_KEY  = 'YOUR_PUBLIC_KEY';
```

---

## 📋 Callback Request System

On the **Let's Connect** page, visitors can submit their name and phone number to request a callback.

- Submissions are saved to `localStorage` under the key `dstech_requests`
- The form validates both fields before saving
- A confirmation message is shown on success
- If the form is toggled **closed** in the dashboard, visitors see a "Connections currently closed" message

---

## ⚙️ Admin Dashboard

**Access:** Click "⚙ Dashboard" in the navigation bar.  

### Dashboard Features

| Feature | Description |
|---------|-------------|
| **Total Requests** | Count of all callback submissions |
| **Today** | Count of submissions received today |
| **Form Status** | Live indicator — Open (pulsing blue dot) or Closed |
| **Toggle Form** | Open/close the contact form for new submissions |
| **Request Cards** | Each card shows: name, date/time, phone number |
| **Delete** | Remove individual requests |
| **Lock** | Re-lock the dashboard |

> ⚠️ **To change the admin password**, search the HTML for `const DASH_PASSWORD = '

---

## 🗂️ File Structure

This is a **single-file website** — everything lives in `dstech.html`:

```
dstech.html
├── <head>
│   ├── Google Fonts (Space Grotesk + Inter)
│   ├── EmailJS CDN (for review notifications)
│   └── <style> — all CSS (design tokens, layout, components, animations)
│
├── <body>
│   ├── Ticker strip (scrolling announcement bar)
│   ├── <nav> — sticky navigation
│   │
│   ├── #page-home       (Home — Hero, Stats, Services, Why, CTA)
│   ├── #page-about      (About — Profile sidebar + bio content)
│   ├── #page-connect    (Let's Connect — callback form)
│   ├── #page-testimonials (Testimonials + Leave a Review)
│   └── #page-dashboard  (Admin dashboard — password protected)
│
└── <script> — all JavaScript
    ├── showPage()        — SPA navigation
    ├── toggleNav()       — mobile hamburger menu
    ├── submitForm()      — callback form + localStorage
    ├── checkDashPass()   — dashboard auth
    ├── toggleForm()      — open/close callback form
    ├── renderDashboard() — render request cards
    ├── deleteRequest()   — remove a request
    ├── submitReview()    — review form + EmailJS
    ├── renderAdminReviews() — admin review panel
    ├── toggleApproveReview() — approve/unapprove
    ├── exportReviews()   — CSV download
    └── deleteReview()    — remove a review
```

---

## 📱 Responsive Design

| Breakpoint | Behavior |
|------------|----------|
| **> 900px** | Full two-column layouts (hero, about, connect) |
| **≤ 900px** | Single column, hero visual hidden, about sidebar stacks |
| **≤ 640px** | Mobile hamburger nav, footer collapses to single column |

---

## 💾 Data Storage

All data is stored in the browser's `localStorage` — no backend or database required.

| Key | Contents |
|-----|----------|
| `dstech_requests` | Array of callback request objects `{id, name, phone, date, time}` |
| `dstech_reviews` | Array of review objects `{id, name, role, email, stars, text, date, time, timestamp, approved}` |

> **Note:** `localStorage` is browser-local and per-device. Data will persist across browser sessions but will not sync across devices. For a production setup, consider connecting a backend (e.g. Firebase, Supabase, or a simple serverless function).

---

## 🚀 Deployment Options

### Option 1 — Open Locally
Download `dstech.html` and open it directly in any modern browser. All features work offline except EmailJS notifications.

### Option 2 — GitHub Pages
1. Create a new GitHub repository
2. Upload `dstech.html` — rename it `index.html`
3. Go to **Settings → Pages → Source → main branch / root**
4. Your site will be live at `https://yourusername.github.io/your-repo`

### Option 3 — Netlify / Vercel (Free)
1. Drag and drop `dstech.html` (renamed `index.html`) onto [netlify.com/drop](https://netlify.com/drop)
2. Get an instant live URL in seconds

### Option 4 — Shopify Theme
A full Shopify OS 2.0 theme version (`dstech-shopify-theme.zip`) is also available with all sections editable in the Shopify Theme Customizer. See the Shopify theme README for setup instructions.

----

## 🛠️ Customization Guide

| What to change | Where to find it |
|---------------|-----------------|
| Business name | Search `DS Tech` — update all instances |
| Owner name | Search `Dasiah Silva` |
| Hero headline | Find `hero-h1` in the home page section |
| Services | Find `services-grid` div — edit or add `.service-card` blocks |
| Testimonials | Find `testimonials-grid` div — edit or add `.testimonial-card` blocks |
| Stats | Find `stats-band` div — update `.stat-num` and `.stat-lbl` |
| Colors | Update CSS variables at `:root` near the top of `<style>` |
| Ticker items | Find `ticker-inner` div — edit `<span class="ticker-item">` elements |
| Footer text | Find `footer-copy` spans |

---

## 👩‍💻 About the Owner

**Dasiah Silva** is an IT & Cybersecurity Specialist with over 3 years of hands-on experience helping individuals, families, and small businesses with:

- IT support and troubleshooting
- Network administration and setup
- Cybersecurity consulting and audits
- Hardware installation and upgrades
- Virus and malware removal
- Data backup and recovery

> *"Technology should empower you — and protecting it should feel personal, not transactional."*

---

## 📞 Contact & Support

- **Website:** DS Tech (this site)
- **Service:** Callback upon request via the Let's Connect page
- **Support:** Remote and on-site available
- **Response time:** Average under 24 hours

---

## 📜 License : Pending

© 2024 DS Tech — All rights reserved.  
*Dasiah Silva — IT & Cybersecurity Specialist*
