# ⚽ World Cup 2026 — Office TV Display

A live match-day display page for the FIFA World Cup 2026, designed to run full-screen on an office TV via GitHub Pages.

Shows today's matches, live scores, and group standings — auto-refreshing every minute.

---

## Setup

### 1. Get a free API key

- Go to [RapidAPI — API-Football](https://rapidapi.com/api-sports/api/api-football)
- Create a free account and subscribe to the **Basic (free)** tier
- Copy your RapidAPI key from the dashboard

### 2. Add your key to the page

Open `worldcup2026-tv.html` and find this line near the top of the `<script>` block:

```js
const RAPIDAPI_KEY = 'PASTE_YOUR_RAPIDAPI_KEY_HERE';
```

Replace `PASTE_YOUR_RAPIDAPI_KEY_HERE` with your actual key.

### 3. Push to GitHub

```bash
git init
git add worldcup2026-tv.html README.md
git commit -m "World Cup 2026 display"
git remote add origin https://github.com/YOUR_USERNAME/YOUR_REPO.git
git push -u origin main
```

### 4. Enable GitHub Pages

- Go to your repo → **Settings** → **Pages**
- Set source to **Deploy from a branch** → `main` → `/ (root)`
- Save — your page will be live at:
  `https://YOUR_USERNAME.github.io/YOUR_REPO/worldcup2026-tv.html`

### 5. Open on the TV

Navigate to your GitHub Pages URL in a full-screen browser on the TV. The page auto-refreshes every minute and handles everything automatically.

---

## ⚠️ Keep your repo PRIVATE

Your RapidAPI key is embedded in the HTML. While the free tier has a 100 req/day cap (so abuse is limited), it's good practice to keep the repository **private** on GitHub. GitHub Pages works with private repos if you're on a free account — just go to Settings → Pages and enable it.

If you ever need to rotate your key, just replace it in the file and push again.

---

## Free tier limits

API-Football's free tier allows **100 requests/day**. The page is designed to stay well within this:

- Standings are cached for 10 minutes (or 2 minutes during live matches)
- Live scores are fetched once per minute only during active games
- A full match day typically uses ~30–50 requests

---

## Features

- Matches kicking off in the next 24 hours
- Live score display with match minute
- FT scores for completed matches
- Group standings (P / W / D / L / Pts) pulled live from API
- Teams playing today highlighted in each group table
- Scrolling ticker with today's fixtures and scores
- Countdown to tournament start (before June 11th)
- Status indicator showing API connection health
