# 🕯️ Literary Clock

An ambient clock inspired by the [Author Clock](https://authorclock.com/) — free, fully customizable, and built to run in the **Echo Show** browser (or on any screen: TV, tablet, phone).

Displays the time, a rotating literary quote, weather with icons, moon phase, celestial events, and the book you're currently reading — with automatic progress sync via Goodreads.

---

## ✨ Features

- **Clock** with refined typography (Cormorant + serif font options)
- **Quotes** that rotate every 30 min through your saved collection
- **Weather** with SVG day/night icons, powered by [Open-Meteo](https://open-meteo.com/) (no API key needed)
- **Moon phase** calculated locally — 8 phases, works offline
- **Celestial events** when something is coming up (solstices, equinoxes, meteor shower peaks)
- **Current book** synced automatically via Goodreads (hourly)
- **Reading progress** in pages (physical book) or percentage (Kindle), with automatic Goodreads sync
- **8 visual themes** including an E-ink Kindle-style palette and a fully custom mode (with color pickers)
- **7 literary fonts**: EB Garamond, Lora, Crimson Pro, Spectral, Playfair Display, Cormorant Garamond, Old Standard TT
- **Echo Show keep-alive** (silent looping audio that prevents Silk from returning to the home screen)
- **Backup & import** to transfer all settings between devices via a JSON code

---

## 🚀 Getting started

### 1. Configure on your computer

Open `index.html` in any browser, click the **gear icon** in the top-right corner, and set up:

- Theme and font
- City (for the weather)
- Your favourite quotes
- Current book and reading progress

### 2. Deploy to GitHub Pages

1. Create a **public** repository on GitHub
2. Upload `index.html` (the filename must be exactly that)
3. Go to **Settings → Pages**, select branch `main`, and save
4. Wait ~1 minute — your URL will appear at the top of the Pages settings

### 3. Open on Echo Show

1. Say **"Alexa, open Silk"**
2. Type in your GitHub Pages URL
3. **Tap the screen once** to activate the keep-alive audio
4. Bookmark it so you can reopen easily

---

## 📚 Goodreads integration

For the current book and progress to update automatically:

1. Make your profile **public** (Settings → Privacy)
2. In the gear → **Now reading** → mode **Goodreads** → paste your **numeric user ID**
   - The ID is in your profile URL: `goodreads.com/user/show/`**`12345678`**`-your-name`
3. For progress sync to work: **post reading progress updates on Goodreads** while you read (the app accepts pages or percentage — useful for Kindle)

Progress is fetched automatically alongside the book. You can also trigger it manually with the **"Fetch from Goodreads"** button in the Progress section.

---

## ⚙️ Transferring settings between devices

In the gear → **Backup / transfer**:
- **Export** → copies a JSON code with all your settings
- **Import** → paste the code on another device to apply everything at once

---

## 🔧 Technical details

- **Zero dependencies** — pure HTML, CSS, and JavaScript, a single file
- **No server required** — runs directly in the browser as a static file
- **APIs used** (client-side only, no key required):
  - [Open-Meteo](https://open-meteo.com/) — weather data
  - [rss2json.com](https://rss2json.com/) — relay for the Goodreads RSS feed (free for personal use)
- **Works offline** for: clock, quotes, moon phase, and celestial events
- **Storage** via `localStorage` — everything stays on the device; no data is sent to external servers (aside from the two API calls above)

---

## 📅 Celestial events included

Solstices, equinoxes, and peaks of major meteor showers visible from the northern hemisphere through mid-2027 (Perseids, Geminids, Lyrids, Quadrantids, and others). The list can be edited directly in `index.html`.

---

## 🎨 Available themes

| Name | Style |
|---|---|
| Auto | Parchment by day, ink by night |
| Parchment | Warm cream, always |
| Sepia | Tea-toned, light |
| E-ink | Paper grey, Kindle-style |
| Night Ink | Dark background, warm gold |
| Forest | Deep green, cream |
| Bordeaux | Wine red, terracotta |
| Blue Mist | Slate blue, gold |
| Custom | You pick the colours |

---

## ⚠️ Known limitations

- The Echo Show's Silk browser may close and return to the home screen after a while; the silent audio keep-alive works around this in most cases, but it's a community workaround that could break with Amazon updates
- rss2json has request limits on the free tier — more than enough for personal use, but for production consider replacing it with your own [Cloudflare Worker](https://workers.cloudflare.com/)
- Goodreads does not expose reading progress in the shelf RSS — progress comes from the activity feed, meaning **you need to post progress updates on Goodreads** for them to be picked up
- StoryGraph, Skoob, and Fable currently have no accessible public APIs

---

*Built by someone who also thinks €300 is a lot to spend on a clock.*
