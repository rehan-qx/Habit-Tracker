<div align="center">

<img src="https://img.shields.io/badge/🌊-HabitFlow-7c6fff?style=for-the-badge&labelColor=0a0a0f" alt="HabitFlow" height="40"/>

### Build better habits — one day at a time.

A beautifully designed, **mobile-first habit tracker** built as a single HTML file.  
No installs. No servers. No accounts. Just open and start.

<br/>

[![Live Demo](https://img.shields.io/badge/🚀_Live_Demo-habittracer.vercel.app-7c6fff?style=for-the-badge&labelColor=1a1535)](https://habittracer.vercel.app)
&nbsp;
[![Version](https://img.shields.io/badge/version-1.0.0-ff6f9c?style=flat-square)](https://habittracer.vercel.app)
[![PWA Ready](https://img.shields.io/badge/PWA-ready-6fffc4?style=flat-square)](#-install-on-mobile-pwa)
[![Works Offline](https://img.shields.io/badge/works-offline-ffb86f?style=flat-square)](#-privacy)
[![License](https://img.shields.io/badge/license-MIT-8888aa?style=flat-square)](#-license)
[![Single File](https://img.shields.io/badge/single-file-7c6fff?style=flat-square)](#️-project-structure)

<br/>

</div>

---

## 📸 Screenshots

> Open on mobile for the best experience — or try the [live demo](https://habittracer.vercel.app) right now.

| Today Dashboard | Challenge Tracker | Stats Page |
|:-:|:-:|:-:|
| _Streak, habits, week view_ | _Countdown ring + day grid_ | _Heatmap + yearly calendar_ |

> 💡 **Tip:** Add to Home Screen on iPhone/Android for a native app feel — no browser bars!

---

## ✨ Features at a Glance

```
🏠 Today      →  Streak, habits, 7-day week strip, progress bar
📊 Stats       →  Heatmap, yearly calendar, habit performance
➕ Add          →  Name, emoji, color, alarm time
🎯 Challenge  →  100-day goals, ring progress, day grid
📲 Install     →  Step-by-step PWA guide for iPhone & Android
```

<details>
<summary><strong>📋 Full Feature List</strong></summary>

<br/>

### 🏠 Today Dashboard
- **Streak counter** — global day streak across all habits
- **Daily completion %** — today's progress at a glance
- **7-day week strip** — visual past 7 days with completion dots
- **Progress bar** — smooth animated habit completion rate
- **Challenge mini card** — live countdown to active goal
- **Habit cards** — tap to mark done/undone with confetti 🎊

### 📊 Stats Page
- **6 overview cards** — Total Habits, Today's Done, Streak, Weekly Rate, Challenge Day, Days Left
- **🔥 4-Week Heatmap** *(collapsible)* — color-coded 28-day activity grid
- **📅 Yearly Calendar** *(collapsible)* — full 12-month view with highlights
- **Habit Performance** — per-habit progress bars + streak badges + Edit button

### ➕ Add Habit
- Custom name (up to 30 characters)
- Emoji picker — 22 options
- Color selector — 8 accent colors
- Optional daily alarm with real audio + vibration

### 🎯 Day Challenge
- Personal goal name (e.g. "Learn Quran", "75 Hard", "Build Muscle")
- Preset durations: **7 / 21 / 30 / 60 / 75 / 100 days**
- Custom days — any value from 1–365
- Circular ring progress with live percentage
- Day grid — every day as a colored box (upcoming / passed / today)
- Reset and restart anytime

### ⏰ Alarm System
- Daily reminder per habit with real **audio beep** (Web Audio API)
- **Vibration** on mobile devices
- **Browser push notification** with habit emoji + name
- In-app alarm banner with one-tap **Mark Done**
- Auto-dismisses after 30 seconds, reschedules for next day

### ✏️ Edit & Delete
- **Edit button** in Stats → Habit Performance
- Bottom sheet modal — edit name, emoji, color, alarm
- **Delete** habit instantly
- All changes saved to localStorage immediately

### 📲 PWA / Mobile Install
- Add to Home Screen — iPhone & Android
- Full-screen, no browser bars
- Works completely **offline** after first load
- Built-in step-by-step install guide

</details>

---

## 🚀 Getting Started

### Option 1 — Try it Online
```
https://habittracer.vercel.app
```
Open in any browser. Zero setup.

---

### Option 2 — Run Locally

**Download the file:**
```bash
git clone https://github.com/your-username/habitflow.git
cd habitflow
```

**Open directly** (simplest):
```bash
open habit-tracker.html          # macOS
start habit-tracker.html         # Windows
xdg-open habit-tracker.html      # Linux
```

**Or serve locally** (recommended for PWA features):
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# Then visit:
# http://localhost:8080/habit-tracker.html
```

---

## 📲 Install on Mobile (PWA)

### 📱 iPhone / iPad
| Step | Action |
|------|--------|
| 1 | Open **https://habittracer.vercel.app** in **Safari** |
| 2 | Tap the **Share** button `📤` at the bottom |
| 3 | Scroll down → tap **"Add to Home Screen"** |
| 4 | Tap **Add** — done! |

### 🤖 Android
| Step | Action |
|------|--------|
| 1 | Open the URL in **Google Chrome** |
| 2 | Tap the **⋮ three-dot menu** (top right) |
| 3 | Tap **"Add to Home screen"** or **"Install app"** |
| 4 | Tap **Install** — done! |

> After installing, HabitFlow opens full-screen like a native app — no browser UI, works offline.

---

## ☁️ Deploy Your Own

### Vercel (Recommended — 1 click)

```bash
npm i -g vercel
vercel deploy
```

Or connect your GitHub repo to [vercel.com](https://vercel.com) → auto-deploys on every push.

---

### Netlify

```bash
npm i -g netlify-cli
netlify deploy --prod --dir .
```

Or drag & drop `habit-tracker.html` at [app.netlify.com/drop](https://app.netlify.com/drop).

---

### GitHub Pages

1. Push to a GitHub repo
2. Go to **Settings → Pages**
3. Source: `main` branch, `/ (root)`
4. Your app is live at `https://username.github.io/repo-name/habit-tracker.html`

---

### Cloudflare Pages

1. Connect your GitHub repo at [pages.cloudflare.com](https://pages.cloudflare.com)
2. Build command: _(leave empty)_
3. Output directory: `/`
4. Done — global CDN, free SSL

---

## 🗂️ Project Structure

```
habitflow/
├── habit-tracker.html    ← Entire app (single file, ~800 lines)
└── README.md             ← This file
```

Everything lives in one self-contained file:

| Section | Description |
|---------|-------------|
| `<head>` | Google Fonts (Syne + DM Sans), PWA meta tags, theme color |
| `<style>` | Dark theme CSS, animations, mobile-safe layout, CSS variables |
| `<body>` | 5 pages: Today · Stats · Add · Challenge · Install |
| `<script>` | State management, alarms, rendering, navigation — ~400 lines |

---

## 💾 Data & Storage

All data lives in your browser's `localStorage` under the key **`hf_v4`**.

### Schema
```json
{
  "habits": [
    {
      "id": 1700000000000,
      "name": "Morning Run",
      "emoji": "🏃",
      "color": "#7c6fff",
      "time": "07:00",
      "streak": 5,
      "completions": {
        "2026-03-01": true,
        "2026-03-23": true
      }
    }
  ],
  "globalStreak": 12,
  "selEmoji": "🏃",
  "selColor": "#7c6fff",
  "challenge": {
    "goalName": "Build Muscle",
    "totalDays": 100,
    "startDate": "2026-01-01"
  }
}
```

### Backup & Restore

**Backup:**
```
Browser DevTools → Application → Local Storage → copy hf_v4 value
```

**Restore:**
```javascript
// Paste this in browser DevTools console:
localStorage.setItem('hf_v4', '<paste your backup here>');
location.reload();
```

---

## ⏰ Alarm System Details

| Layer | Technology | Works when closed? |
|-------|-----------|-------------------|
| 🔊 Sound | Web Audio API (generated beep) | ❌ Requires tab open |
| 📳 Vibration | Vibration API | ❌ Requires tab open |
| 🔔 Push Notification | Notification API | ✅ While browser runs |

> The app requests notification permission on first load — click **Allow** to enable push alerts.

> **Note:** True background alarms (when browser is fully closed) require a Service Worker, which is on the roadmap.

---

## 🎨 Design System

### Color Palette
| Variable | Hex | Usage |
|----------|-----|-------|
| `--bg` | `#0a0a0f` | Page background |
| `--s1` | `#13131a` | Card surface |
| `--s2` | `#1c1c27` | Elevated surface |
| `--bd` | `#2a2a3a` | Borders |
| `--a` | `#7c6fff` | Primary accent — violet |
| `--b` | `#ff6f9c` | Secondary accent — pink |
| `--c` | `#6fffc4` | Success — mint green |
| `--t` | `#f0f0ff` | Primary text |
| `--td` | `#8888aa` | Dimmed text |
| `--tf` | `#44445a` | Faint text |

### Typography
- **[Syne](https://fonts.google.com/specimen/Syne)** `700, 800` — headings, numbers, labels
- **[DM Sans](https://fonts.google.com/specimen/DM+Sans)** `400, 500, 600` — body, inputs

### Mobile Safety
- Uses `env(safe-area-inset-*)` for iPhone notch, Dynamic Island, and Android gesture bars
- `viewport-fit=cover` for edge-to-edge display
- Touch targets sized for comfortable mobile use

---

## 🛠️ Customization

### Rename the App
Search and replace `HabitFlow` throughout the file.

### Add Emojis
```javascript
// Find this array in <script>:
const EMOJIS = ['🏃','💪','📚', ...];
// Add any emoji to the list
```

### Add Colors
```javascript
const COLORS = ['#7c6fff','#ff6f9c', ...];
// Add any hex color
```

### Edit Default Habits
```javascript
habits: [
  { id: 1, name: 'Morning Run', emoji: '🏃', color: '#7c6fff', time: '07:00', streak: 0, completions: {} },
  // Add or remove as needed
],
```

### Change Theme
Edit the CSS variables in `:root { }` — the entire app's colors update instantly.

---

## 📋 Browser Compatibility

| Browser | Version | Support |
|---------|---------|---------|
| Chrome / Edge | 90+ | ✅ Full |
| Safari (iOS / macOS) | 14+ | ✅ Full |
| Firefox | 90+ | ✅ Full |
| Samsung Internet | 14+ | ✅ Full |
| Opera | 76+ | ✅ Full |

**Requirements:** ES6+, CSS Custom Properties, localStorage, Web Audio API, Notification API

---

## 🔒 Privacy

| | |
|--|--|
| 📡 Data sent to server | **None** |
| 🍪 Cookies | **None** |
| 📊 Analytics / Tracking | **None** |
| 🔐 Account required | **No** |
| 📦 Data location | Your device only (`localStorage`) |

Works 100% offline after first load. Fonts (Google Fonts) require internet on first visit only — self-host the fonts to remove this dependency entirely.

---

## 🐛 Known Limitations

- **No cloud sync** — data is local to each browser/device
- **No cross-device backup** — manual export via DevTools only  
- **Background alarms** — requires browser tab open (no Service Worker yet)
- **Streak logic** — resets if a day is missed; no retroactive completion
- **Yearly calendar** — current year only

---

## 🗺️ Roadmap

- [ ] Service Worker — true offline + background alarm notifications
- [ ] JSON export / import — cross-device backup
- [ ] Multiple simultaneous challenges
- [ ] Weekly & monthly summary reports
- [ ] Habit categories and tags
- [ ] Light / dark theme toggle
- [ ] Habit template packs (fitness, study, wellness)
- [ ] Notes per habit completion

---

## 🤝 Contributing

Contributions are welcome! Since this is a single-file project, the workflow is simple:

```bash
# 1. Fork the repo
# 2. Edit habit-tracker.html
# 3. Test in browser (mobile recommended)
# 4. Open a Pull Request
```

**Areas where help is appreciated:**
- Service Worker implementation
- JSON backup/restore UI
- Accessibility improvements
- RTL language support

---

## 📄 License

```
MIT License — Copyright (c) 2026 HabitFlow

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in
all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 🙏 Credits

Built with open web standards — no frameworks, no build tools, no dependencies.

| Technology | Purpose |
|-----------|---------|
| [Syne](https://fonts.google.com/specimen/Syne) + [DM Sans](https://fonts.google.com/specimen/DM+Sans) | Typography |
| [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) | Alarm beep sound |
| [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) | Push notifications |
| [Vibration API](https://developer.mozilla.org/en-US/docs/Web/API/Vibration_API) | Mobile haptic feedback |
| [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) | Data persistence |

---

<div align="center">

**⭐ If HabitFlow helps you build better habits, consider starring the repo!**

<br/>

[![Live Demo](https://img.shields.io/badge/Try_it_Now-habittracer.vercel.app-7c6fff?style=for-the-badge&labelColor=1a1535)](https://habittracer.vercel.app)

<br/>

_Made with 🌊 — Build habits, change your life._

</div>
