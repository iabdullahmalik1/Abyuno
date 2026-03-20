# abyUNO — Free Multiplayer UNO Card Game

<p align="center">
  <img src="logo.png" alt="abyUNO Logo" width="220">
</p>

<p align="center">
  <strong>Play classic UNO online with friends — free, instant, no downloads.</strong><br>
  Real-time multiplayer · 2–8 players · Works on mobile &amp; desktop
</p>

<p align="center">
  <a href="https://abyuno.online/">🎮 Play Now</a> ·
  <a href="https://abyuno.online/privacy.html">Privacy Policy</a> ·
  <a href="https://abyuno.online/terms.html">Terms of Service</a>
</p>

---

## What is Abyuno?

**Abyuno** is a premium, browser-based multiplayer UNO card game built as a single `index.html` file. No frameworks, no bundler, no installation — just open the link and play. It uses Firebase for real-time multiplayer, Google Auth for sign-in, and EmailJS for notifications.

---

## Features

| Feature | Details |
|---|---|
| 🎮 Multiplayer | 2–8 players per room, real-time via Firebase |
| 🔒 Private Rooms | 6-character shareable room codes |
| 🌐 Public Lobbies | Browse and join open games instantly |
| 👥 Friends System | Add friends, see online status, send challenges |
| ⚡ Challenges | Challenge friends even when they're offline |
| 📧 Email Notifications | Welcome, challenge, and friend request emails via EmailJS |
| 🔔 Push Notifications | Browser push via Service Worker |
| 💬 In-Game Chat | Real-time chat with emoji reactions + unread badge |
| 🎨 3 Themes | Midnight, Ocean, Sunset — saved to localStorage |
| 📱 Mobile-Optimised | Responsive for all screen sizes, touch-friendly cards |
| ♻️ Reconnect | Auto-reconnects if browser is accidentally closed |
| 🃏 Proper UNO Rules | Full rule set including first-card effects, draw penalties |
| ⏱ Turn Timer | 30-second turn timer with auto-draw |
| 🏆 Results Screen | Winner announcement, rankings, confetti |

---

## UNO Rules Implemented

- Match by **colour** or **number**
- **Skip** — next player loses their turn (matches colour or another Skip)
- **Reverse** — flips direction; in 2-player acts as a Skip
- **Draw Two (+2)** — next player draws 2 cards and keeps their turn (can play if matching)
- **Wild** — change the current colour (always playable)
- **Wild Draw Four (+4)** — change colour, next player draws 4 and keeps their turn
- **First card rules** — Skip/Reverse/+2 on first card apply immediately
- **UNO** — must press when you have 2 cards. Penalty: **5 cards** if you forget
- **Draw rule** — draw 1; if playable, you may play it; otherwise turn passes

---

## Tech Stack

```
Frontend    Vanilla JavaScript (ES2020+) + HTML5 Canvas
Auth        Firebase Authentication (Google Sign-In)
Database    Firebase Firestore (game state, users, friends)
Realtime    Firebase Realtime Database (presence system)
Email       EmailJS (challenge, welcome, friend request emails)
Hosting     GitHub Pages / any static host
Ads         Google AdSense (hub footer + post-game)
```

---

## File Structure

```
abyuno/
├── index.html      ← Entire game (HTML + CSS + JS, single file)
├── logo.png        ← Game logo (also used as favicon + OG image)
├── privacy.html    ← Privacy Policy (required for AdSense)
├── terms.html      ← Terms of Service (required for AdSense)
├── sitemap.xml     ← XML sitemap for Google Search Console
├── robots.txt      ← Crawler instructions
└── README.md       ← This file
```

---

## SEO / AdSense Structure

Abyuno is optimised for Google search, AdSense approval, and AI answer engines:

| Signal | Implementation |
|---|---|
| **Title & Meta** | Keyword-rich, unique per page |
| **Canonical URL** | `<link rel="canonical">` on every page |
| **JSON-LD** | VideoGame, WebApplication, WebSite, FAQPage, HowTo, BreadcrumbList |
| **OG / Twitter** | Full Open Graph and Twitter Card tags |
| **Sitemap** | `sitemap.xml` submitted to Search Console |
| **robots.txt** | Allows all crawlers, blocks Firebase internals |
| **Privacy Policy** | Required by AdSense — `privacy.html` |
| **Terms of Service** | Required by AdSense — `terms.html` |
| **AdSense Placements** | Hub footer (horizontal) + post-game (rectangle) |
| **SEO Content Block** | Crawlable keyword-rich text for the SPA |
| **Core Web Vitals** | Single file, no framework overhead, minimal blocking resources |

---

## Performance Optimisations

- **Zero Firestore reads during gameplay** — `MY_HAND` cached via `onSnapshot`; `GS` cached in memory
- **All game actions are single batch writes** — no sequential reads
- **`sysMsg` is fire-and-forget** — never blocks gameplay
- **Realtime hand listener** — hand updates instantly without polling
- **Opponent hand writes batched** — draw2/wild4 written in the same batch as game state

---

## Screenshots

> Coming soon — add screenshots of gameplay, lobby, and themes here.

---

## Roadmap

- [ ] Spectator mode
- [ ] Game statistics and win/loss history
- [ ] Custom card themes
- [ ] Tournament mode (bracket)
- [ ] Sound effects
- [ ] Progressive Web App (PWA) manifest

---

## Contributing

Pull requests are welcome! Please open an issue first to discuss what you'd like to change.

---

## License

This project is licensed under the MIT License. See [LICENSE](LICENSE) for details.

> **Note:** UNO is a registered trademark of Mattel, Inc. This project is an independent fan-made implementation and is not affiliated with or endorsed by Mattel.

---

## Developer

**Muhammad Abdullah Malik**  
🌐 [abdullahportfolio.site](https://abdullahportfolio.site)  
📧 i.abdullahmalik21@gmail.com

<p align="center">Made with ♥ in Pakistan</p>
