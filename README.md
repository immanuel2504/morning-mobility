# 🌅 Morning Mobility, Posture & Strength App

A polished, installable workout app (PWA) that guides you through your full morning routine
(neck, shoulders, thoracic spine, posture, ankles, pelvic floor + strength).

No accounts, works offline once installed, light & dark themes.

## 📁 Files in this folder
- `index.html` — the app
- `manifest.webmanifest`, `sw.js`, `icon.svg` — make it installable + work offline
- `media/` — drop your own demo clips here (see `media/README.txt`)

---

## ▶️ How to run it

### On your computer
- **Quick look:** double-click **`index.html`** — opens in your browser.
- **Full app mode (install, offline, app icon):** these require the files to be *served* over
  http(s), not opened as a `file://`. Easiest local way:
  1. Open a terminal in this folder.
  2. Run: `python -m http.server 8000`
  3. Visit **http://localhost:8000** in Chrome/Edge → menu → **Install app**.

---

## 📱 How to see it on your phone

You have three good options, from easiest to most "real app".

### Option A — Put it online for free (best; gives a real installable app) ⭐
1. Go to **https://app.netlify.com/drop**
2. **Drag this whole folder** onto the page.
3. Netlify gives you a public link like `https://your-name.netlify.app`.
4. Open that link on your phone (Chrome on Android / Safari on iPhone).
5. Tap the browser menu → **"Add to Home Screen" / "Install app"**.
6. It now opens full-screen like a native app, works offline, and has its own icon. 🎉

(GitHub Pages or Vercel work the same way if you prefer those.)

### Option B — Same Wi-Fi, no upload
1. On your computer, in this folder run: `python -m http.server 8000`
2. Find your computer's local IP (e.g. `192.168.1.20`).
3. On your phone (same Wi-Fi) open: `http://192.168.1.20:8000`

### Option C — Copy the files to the phone
Copy the whole folder to your phone and open `index.html`. This works, but **install and
offline mode need Option A or B** (a real web address), so Option A is recommended.

> Your progress is saved on the device/browser you use, so stick with the same one each day.

---

## 📱 What the app does

- **Routine tab** – All 21 exercises grouped by phase. Tap any one to open it, tap
  **▶ Start Routine** to flow through everything in order, or **↻ Resume** to jump to the
  first exercise you haven't finished yet.
- **Guided player**:
  - ⏱️ **Timed moves** (breathing, stretches, holds) get a countdown ring with start/pause,
    a beep + vibration when finished, last-3-seconds warning ticks, and auto-switching
    between **left/right sides** and rounds.
  - 🔢 **Rep moves** (push-ups, chin tucks, etc.) get a tap counter with set tracking.
  - 😴 **Rest breaks** between exercises with a countdown, a "next up" preview, a **+15s**
    button, and **Skip**.
  - 🗣️ **Voice coaching** announces the exercise name and side switches.
  - 🎉 A **celebration screen** when you finish the whole routine.
- **⚙️ Settings** (tap the gear, top-right) – all saved automatically:
  - Sound cues on/off
  - Voice coaching on/off
  - Auto-advance (move to the next exercise automatically after rest)
  - Keep screen awake during the workout
  - **Essentials only** (skips the optional warm-towel step)
  - Adjustable rest length (0–120 seconds)
- **Checklist tab** – The classic daily tick-box list.
- **Progress tab** – Current streak 🔥, best streak, total days, and a 28-day calendar.
- **Plan tab** – The Weeks 1–2 / 3–4 / 5–8 progression.
- **🎨 Light & dark themes** – tap the moon/sun icon (top-right). Follows your phone's
  system theme by default.
- **📲 Installable (PWA)** – when served over a web address, an "Install" banner appears so
  you can add it to your home screen and use it offline.

## 🎬 Demo animations / videos

Each exercise screen has a **▶ Watch a demo on YouTube** button (opens a relevant how-to
search in your browser).

You can also show your **own looping animation right inside the app**: drop a video or GIF
into the `media/` folder named after the exercise (e.g. `media/deadhang.mp4`), and it plays
automatically on that exercise's screen. See `media/README.txt` for the full list of filenames.

---

## 🔧 Want to change something?

Everything lives in `index.html`. To edit the exercises, find the `EXERCISES` list near the
top of the `<script>` section. Each exercise looks like this:

```js
{ id:'deadhang', phase:'Phase 5 · Hanging', name:'Dead Hang', icon:'🧗',
  type:'timed', duration:15, rounds:3, prescr:'3 rounds · 10–20 sec',
  steps:[...], focus:[...] }
```

- `type:'timed'` → uses a countdown (`duration` in seconds, optional `rounds`, `sides:true`).
- `type:'reps'`  → uses a counter (`reps`, optional `sets`, `holdSec`, `sides:true`).

Change a number, save, refresh the page.

---

## ⚠️ Note
This is a personal training aid, not medical advice. If any movement causes pain,
stop and check with a physiotherapist or doctor.
