# SkillMatch

**Your GitHub already wrote your résumé.**

Drop in a GitHub username and SkillMatch reads the public repositories, works out what skills you actually use, and shows matching remote jobs — all in one single HTML file, with no backend, no signup, and no setup.

---

## What it does

1. **Scan a GitHub profile** — Enter any username (or paste a profile link) and the tool reads that person's public repositories.
2. **Detect real skills** — Instead of asking you to type out a skill list, it looks at the actual languages and topics used across your repos and ranks them by how often they show up. You can also manually add any skill it missed.
3. **Show matching remote jobs** — Based on your top detected skills, it pulls live remote job listings and ranks them by how closely they match your profile.
4. **Browse your projects** — See your public repositories as clean cards, complete with stars, language, and a one-click "Live preview" link for any repo that has a deployed site.
5. **Generate a shareable card** — Turn your profile into a polished, downloadable image card (with your skills, top project, language breakdown, job-match score, and a scannable QR code back to your GitHub) — ready to post on LinkedIn or Twitter.

---

## How it works (step by step)

### 1. Reading your GitHub profile
When you type in a username, the tool fetches your public profile info (name, avatar, bio, follower count) and the full list of your public repositories — skipping any forked repos, since those don't reflect your own original work.

### 2. Turning repos into a skill profile
For every repo you own, the tool looks at two things:
- The **primary language** GitHub detected for that repo
- Any **topics/tags** you've manually added to the repo on GitHub

Each of these is converted into a normalized skill name (so "reactjs," "react-js," and "React" all become just "react"), and every appearance adds to that skill's score. Topics count slightly more than languages, since tagging a topic is something you do on purpose — it's a stronger signal of what you actually consider your skill. The result is a ranked list of your top skills, shown as clickable chips. You can turn any skill off to narrow the job search, or type in your own skill if something's missing.

### 3. Finding matching jobs
Your top skills are used to pull a batch of current remote job listings. Each listing is then scored against your *currently active* skill chips — the more of your skills that show up in a job's title, tags, or category, the higher its match score. Jobs are sorted highest-match first and shown as cards with a circular match-percentage ring, company name, tags, location, and a direct apply link. Turning skill chips on/off live-updates this list instantly, with no new network request needed.

### 4. Showing your projects
Your repositories are displayed as a separate grid, sorted by star count. If a repo has GitHub Pages enabled, a "Live preview" badge and link appear, opening the deployed site directly in a new tab.

### 5. Building the shareable card
This is the most visual part of the tool. When you switch to the "Card" view, the tool draws a complete portfolio card onto a canvas in real time:
- Your avatar (pulled live, with a graceful colored-initial fallback if the image can't load)
- Your name, username, repo/follower counts
- Your top skills as rounded chips
- A **language mix bar** showing the proportion of each language across your repos
- Your **highest-starred project**, named and counted
- Your **best current job-match percentage**, shown as a bold badge
- A **scannable QR code** that links straight back to your GitHub profile
- Four switchable color themes (Violet, Sunset, Midnight, Forest)

Once you're happy with it, one click downloads the whole thing as a PNG image, sized for LinkedIn and Twitter.

### 6. Everything else
- **Dark / light mode** — toggle in the header, with a fully separate color palette for each so contrast stays clean either way.
- **Visit counter** — a small badge in the header tracks how many times the page has loaded.
- Searching for a new username instantly clears out the old profile's data, so nothing stale lingers on screen.

---

## What makes this different

Most tools that do "GitHub → career insights" require you to install something, run a build step, or get an API key before they'll work. SkillMatch is the opposite: it's one HTML file. Open it in a browser, type a username, and you're done. There's no server, no database, no account, and nothing is ever stored — every search happens fresh, live, in your browser.

---

## Tech notes

- 100% client-side — a single `index.html` file, no build tools, no installation
- Styled with Tailwind CSS (loaded via CDN)
- All visuals (charts, cards, rings) are drawn natively rather than using heavy charting libraries
- The shareable card is rendered on an HTML canvas; the QR code is the one small external library the project depends on
- Works on desktop and mobile, with a layout that adapts down to small screens

---

## Credits

Developed by ❤️ **Reehan MP**.
