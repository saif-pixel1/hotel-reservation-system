# 🏨 Hotelier — Luxury Hotel Reservations

> A fully client-side hotel booking experience. No backend. No build step. No dependencies.
> Open `index.html` and everything works — search, filter, compare, book, and manage.

![Status](https://img.shields.io/badge/status-demo-a8742a)
![License](https://img.shields.io/badge/license-MIT-10302b)
![Dependencies](https://img.shields.io/badge/dependencies-none-1f7a54)
![Size](https://img.shields.io/badge/total%20size-~60KB-587069)

---

## Table of contents

1. [What this is](#what-this-is)
2. [Feature tour](#feature-tour)
3. [Quick start](#quick-start)
4. [Project structure](#project-structure)
5. [Architecture](#architecture)
6. [Data model](#data-model)
7. [Pricing & tax math](#pricing--tax-math)
8. [The booking flow](#the-booking-flow)
9. [Admin dashboard](#admin-dashboard)
10. [Plain-word search & assistant](#plain-word-search--assistant)
11. [3D tower](#3d-tower)
12. [Theming & design tokens](#theming--design-tokens)
13. [Persistence & localStorage keys](#persistence--localstorage-keys)
14. [Function reference](#function-reference)
15. [Customization guide](#customization-guide)
16. [Deployment](#deployment)
17. [Accessibility](#accessibility)
18. [Browser support](#browser-support)
19. [Known limitations](#known-limitations)
20. [Roadmap](#roadmap)
21. [Troubleshooting](#troubleshooting)
22. [License](#license)

---

## What this is

Hotelier is a **single-page hotel reservation demo** built from three files:

| File | Purpose | Lines (approx.) |
|------|---------|-----------------|
| `index.html` | Markup, dialogs, 3D stage, assistant panel | ~60 |
| `style.css` | Design tokens, layout, responsive rules, CSS-3D | ~90 |
| `script.js` | State, rendering, booking flow, admin, assistant, 3D | ~130 |

The whole app runs **entirely in the browser**. Bookings, saved rooms, and recently-viewed history are stored in `localStorage` on the visitor's device. Nothing is sent to a server. There is no login, no payment integration, and no real inventory — it's a polished, realistic frontend you can wire to a real API later.

It ships with **28 seeded sample reservations** so the admin dashboard looks populated on first load.

---

## Feature tour

### 🔍 Search & discovery
- **Hero search** — check-in date, check-out date, guest count.
- **Plain-word search** — type `"Family room with parking and breakfast, below ₹6,000"` and the parser sets budget, guests, and amenity filters automatically.
- **Live filters** — max-price slider (₹2,000–₹12,000), amenity chips (Wi-Fi, Breakfast, Parking, Pool, Spa, Balcony, Kitchen, Workspace), and sort (recommended / price ↑ / price ↓ / rating).
- **Smart recommendations** — room scores factor in your saved rooms and recently viewed rooms, so "Selected for you" adapts to *you*.

### 🛏 Rooms & comparison
- 6 room types with images, prices, capacity, ratings, and amenities.
- **Save (♡)** rooms — persisted.
- **Compare (⚖)** up to 3 rooms. The compare table highlights **lowest price**, **largest capacity**, **top rating**, and **best value** (rating per ₹1,000).
- A floating **compare bar** appears as you select rooms.

### 🏢 3D tower explorer
- CSS-only pseudo-3D building you can **drag to spin**.
- **Tap a floor** to inspect the room and book it.
- **💥 Explode tower** pulls the floors apart. Same button rebuilds.
- Respects `prefers-reduced-motion`.

### 📅 Booking flow (4 steps)
1. **Dates** — calendar with unavailable nights struck through.
2. **Guests & extras** — party size + breakfast / airport pickup / spa credit.
3. **Review** — guest name, email, phone (all validated) with a live price breakdown including tax.
4. **Done** — reference code, digital-key barcode, confetti.

### 📊 Admin dashboard
- Reservation count, total revenue, occupancy (last 30 days), cancellation rate.
- **Revenue by month** and **Bookings by room** bar charts.
- **Latest bookings** table with per-row **Cancel** button.

### ✦ Assistant
- Chat panel with inline "book" buttons for matched rooms.
- **Voice input (🎤)** via Web Speech API (Chromium browsers only).
- **Spoken replies** after a voice query.

### 🖼 Gallery & lightbox
- Six interior shots with fullscreen viewer (prev/next/close).

### 🌗 Theming
- Light/dark toggle (**◐**) with `prefers-color-scheme` as the default.

---

## Quick start

### Option 1 — Just open it
```bash
# Download the three files + images/ folder, then:
open index.html      # macOS
xdg-open index.html  # Linux
start index.html     # Windows
