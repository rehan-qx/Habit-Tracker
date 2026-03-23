# 🌊 HabitFlow

> A beautifully designed, mobile-first habit tracker — built as a single HTML file. No installs, no servers, no accounts. Just open and start building better habits.

![HabitFlow](https://img.shields.io/badge/version-1.0.0-7c6fff?style=flat-square) ![License](https://img.shields.io/badge/license-MIT-ff6f9c?style=flat-square) ![PWA](https://img.shields.io/badge/PWA-ready-6fffc4?style=flat-square) ![Offline](https://img.shields.io/badge/works-offline-ffb86f?style=flat-square)

---

## 📱 Live Demo

Simply open `habit-tracker.html` in any modern browser — it works instantly. No build step, no dependencies, no backend.

---

## ✨ Features

### 🏠 Today Dashboard
- **Streak counter** — tracks your global day streak across all habits
- **Daily completion %** — shows today's progress at a glance
- **7-day week strip** — visual view of the past 7 days with completion dots
- **Progress bar** — smooth animated bar showing today's habit completion rate
- **Challenge mini card** — live countdown to your active challenge goal
- **Habit cards** — tap to mark done/undone with confetti celebration

### 📊 Stats Page
- **6 overview cards** — Total Habits, Today's Done, Streak, Weekly Rate, Challenge Day, Days Remaining
- **🔥 4-Week Heatmap** *(collapsible)* — color-coded activity grid for the past 28 days
- **📅 Yearly Calendar** *(collapsible)* — full 12-month view with habit completion highlights
- **Habit Performance** — per-habit progress bars with streak badges and Edit button

### ➕ Add Habit
- Custom **habit name** (up to 30 characters)
- **Emoji picker** — 22 emoji options
- **Color selector** — 8 accent colors
- **Alarm time** — optional daily reminder with real audio + vibration

### 🎯 Day Challenge
- Set a personal goal (e.g. "Lose 10kg", "Learn Quran", "75 Hard")
- **Preset durations**: 7 / 21 / 30 / 60 / 75 / 100 days
- **Custom days** — enter any value from 1–365
- **Circular ring progress** with percentage
- **Day grid visualization** — every day shown as a colored box (upcoming / passed / today)
- Live countdown showing current day and days remaining
- Reset and restart anytime

### ⏰ Alarm System
- Set a daily reminder time per habit
- **Audio beep** plays at alarm time (Web Audio API)
- **Vibration** on supported mobile devices
- **Browser push notification** with the habit's name
- **In-app alarm banner** slides down with habit emoji and name
- One-tap **Mark Done** directly from the alarm
- Auto-dismisses after 30 seconds and reschedules for the next day

### ✏️ Edit & Delete
- Tap **Edit** button in Stats → Habit Performance
- Edit name, emoji, color, alarm time in a smooth **bottom sheet modal**
- **Delete** habit with confirmation button
- Changes saved instantly to local storage

### 📲 Mobile Install (PWA)
- Full **Add to Home Screen** support for iPhone and Android
- Runs **full-screen** with no browser chrome
- Works completely **offline** after first load
- Step-by-step install guide built into the app

---

## 🚀 Getting Started

### Option 1 — Open Directly
```bash
# Just double-click the file, or:
open habit-tracker.html
```

### Option 2 — Serve Locally
```bash
# Python
python -m http.server 8080

# Node.js
npx serve .

# Then open: http://localhost:8080/habit-tracker.html
```

### Option 3 — Deploy Online
Upload `habit-tracker.html` to any static host:
- **GitHub Pages** — push to a repo, enable Pages
- **Netlify** — drag and drop the file
- **Vercel** — `vercel deploy`
- **Cloudflare Pages** — connect your repo

---

## 📲 Install on Mobile (PWA)

### iPhone / iPad
1. Open the URL in **Safari** (not Chrome)
2. Tap the **Share** button `📤` at the bottom
3. Scroll down and tap **"Add to Home Screen"**
4. Tap **Add** — done!

### Android
1. Open the URL in **Google Chrome**
2. Tap the **⋮ three-dot menu** (top right)
3. Tap **"Add to Home screen"** or **"Install app"**
4. Tap **Install** — done!

> **Note:** After installing, the app opens full-screen with no browser bars, just like a native app.

---

## 🗂️ Project Structure

```
habit-tracker.html        ← The entire app (single file)
README.md                 ← This file
```

The entire application lives in one self-contained HTML file:

| Section | What it does |
|---|---|
| `<head>` | Fonts (Google Fonts: Syne + DM Sans), meta tags for PWA |
| `<style>` | All CSS — dark theme, animations, responsive layout |
| `<body>` | 5 pages: Today, Stats, Add, Challenge, Install |
| `<script>` | All JavaScript — state management, alarms, rendering, navigation |

---

## 💾 Data & Storage

All data is stored locally in the browser using `localStorage` under the key `hf_v4`.

### Data Schema
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
        "2025-03-01": true,
        "2025-03-02": true
      }
    }
  ],
  "globalStreak": 12,
  "selEmoji": "🏃",
  "selColor": "#7c6fff",
  "challenge": {
    "goalName": "Build Muscle",
    "totalDays": 100,
    "startDate": "2025-01-01"
  }
}
```

### Important Notes
- Data is **device-specific** — it lives in the browser on the device you use
- Clearing browser data / site data will erase all habits
- To **back up**, open browser DevTools → Application → Local Storage → copy the `hf_v4` value
- To **restore**, paste the value back into `hf_v4` via DevTools console: `localStorage.setItem('hf_v4', '<paste>')`

---

## ⏰ Alarm & Notifications

HabitFlow uses three layers for alarms:

| Layer | How it works | Works when app is closed? |
|---|---|---|
| **Web Audio API** | Generates a beep tone in-browser | ❌ No |
| **Vibration API** | Vibrates the device | ❌ No |
| **Notification API** | Browser push notification with habit name | ✅ Yes (if browser is running) |

> **Permission required:** The app asks for notification permission on first load. Click **Allow** to enable push notifications.

> **Limitation:** Since HabitFlow is a plain HTML file (not a Service Worker PWA), notifications only fire while the browser is open. For background notifications, the page must be open in at least one tab.

---

## 🎨 Design System

### Color Palette
| Variable | Value | Usage |
|---|---|---|
| `--bg` | `#0a0a0f` | Page background |
| `--s1` | `#13131a` | Card surface |
| `--s2` | `#1c1c27` | Elevated surface |
| `--bd` | `#2a2a3a` | Borders |
| `--a` | `#7c6fff` | Primary accent (violet) |
| `--b` | `#ff6f9c` | Secondary accent (pink) |
| `--c` | `#6fffc4` | Success / mint green |
| `--t` | `#f0f0ff` | Primary text |
| `--td` | `#8888aa` | Dimmed text |
| `--tf` | `#44445a` | Faint text |

### Typography
- **Syne** (700, 800) — headings, numbers, labels
- **DM Sans** (400, 500, 600) — body text, inputs

### Safe Areas
Uses CSS `env(safe-area-inset-*)` for proper iPhone notch / Dynamic Island / home bar spacing.

---

## 🛠️ Customization

### Change App Name
Search for `HabitFlow` in the file and replace with your desired name.

### Add More Emojis
Find the `EMOJIS` array in the `<script>` section:
```javascript
const EMOJIS = ['🏃','💪','📚', ...];
```
Add any emoji to this array.

### Add More Colors
Find the `COLORS` array:
```javascript
const COLORS = ['#7c6fff','#ff6f9c', ...];
```
Add any hex color.

### Change Default Habits
Find the default `state` object and edit the `habits` array:
```javascript
habits: [
  { id: 1, name: 'Morning Run', emoji: '🏃', color: '#7c6fff', time: '07:00', streak: 0, completions: {} },
  // Add or remove habits here
],
```

### Change Theme Colors
Edit the CSS variables in `:root { }` at the top of the `<style>` block.

---

## 📋 Browser Compatibility

| Browser | Support |
|---|---|
| Chrome / Edge 90+ | ✅ Full |
| Safari 14+ (iOS / macOS) | ✅ Full |
| Firefox 90+ | ✅ Full |
| Samsung Internet 14+ | ✅ Full |
| Opera 76+ | ✅ Full |

**Minimum requirements:** ES6+, CSS Variables, localStorage, Web Audio API

---

## 🔒 Privacy

- **Zero data collection** — nothing is sent anywhere
- **No analytics**, no tracking, no cookies
- **No account required**
- All data stays on your device in `localStorage`
- Works 100% offline after first load (fonts require internet on first visit unless self-hosted)

---

## 🐛 Known Limitations

- **No cloud sync** — data is local to each device/browser
- **No cross-device backup** — manual export via DevTools only
- **Alarms require browser open** — no true background notifications without a Service Worker
- **Streak logic** — streak resets if you miss a day; no retroactive completion
- **Yearly calendar** — shows current year only

---

## 🗺️ Roadmap / Future Ideas

- [ ] Service Worker for true offline + background alarms
- [ ] Export / import habits as JSON
- [ ] Multiple challenges simultaneously
- [ ] Weekly/monthly summary reports
- [ ] Habit categories and filtering
- [ ] Dark / light theme toggle
- [ ] Habit templates (fitness, study, wellness packs)
- [ ] Notes per habit completion

---

## 📄 License

MIT License — free to use, modify, and distribute.

```
MIT License

Copyright (c) 2025 HabitFlow

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
```

---

## 🙏 Credits

Built with:
- [Syne](https://fonts.google.com/specimen/Syne) & [DM Sans](https://fonts.google.com/specimen/DM+Sans) — Google Fonts
- [Web Audio API](https://developer.mozilla.org/en-US/docs/Web/API/Web_Audio_API) — alarm sounds
- [Notification API](https://developer.mozilla.org/en-US/docs/Web/API/Notifications_API) — push notifications
- [localStorage](https://developer.mozilla.org/en-US/docs/Web/API/Window/localStorage) — data persistence

---

<div align="center">

**Made with 🌊 — Build habits, change your life.**

</div>
