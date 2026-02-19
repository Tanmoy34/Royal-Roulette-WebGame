# 🎡 Royal Roulette — Web Game

> A fully playable European single-zero roulette game built from scratch with vanilla HTML5 Canvas, CSS, and JavaScript.  
> **No frameworks. No libraries. Just pure browser technology.**

<br>

[![Live Demo](https://img.shields.io/badge/▶%20Play%20Now-Live%20Demo-blue?style=for-the-badge)](https://tanmoy34.github.io/)
[![HTML5](https://img.shields.io/badge/HTML5-Canvas%20API-E34F26?style=for-the-badge&logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/API/Canvas_API)
[![CSS3](https://img.shields.io/badge/CSS3-Animations-1572B6?style=for-the-badge&logo=css3&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/CSS)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E?style=for-the-badge&logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)
[![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)](LICENSE)

---

## 📖 Table of Contents

- [About the Project](#-about-the-project)
- [Live Demo](#-live-demo)
- [Gameplay](#-gameplay)
- [Bet Types & Payouts](#-bet-types--payouts)
- [Controls](#-controls)
- [Features](#-features)
- [Technical Implementation](#-technical-implementation)
- [Project Structure](#-project-structure)
- [Getting Started](#-getting-started)
- [Author](#-author)

---

## 🎮 About the Project

**Royal Roulette** is a fully functional casino-style roulette game running entirely in the browser, built with **vanilla HTML5 Canvas, CSS3, and JavaScript** — zero external dependencies.

The game faithfully recreates the **European Single Zero** roulette experience: a 37-pocket wheel (0–36), authentic pocket sequence, smooth animated spins, a complete betting table with four bet categories, casino-style chip selection, and a full payout system. The luxury dark gold aesthetic is designed to feel like a real casino floor, not a browser toy.

Built as a personal project to push the limits of what is possible with the browser's native Canvas API — covering custom physics-inspired easing, precise angle mathematics for wheel landing, and a fully responsive layout that works equally well on desktop and mobile.

---

## 🌐 Live Demo

**👉 [Play it here on the portfolio](https://tanmoy34.github.io/)**

Fully playable in any modern browser. No installation, no login, no download required.  
Optimised for both desktop and mobile.

---

## 🕹️ Gameplay

1. Start with **1,000 coins**
2. Choose a **bet type** from the tabs — Outside Bets, Dozens, Columns, or a specific Number
3. Select a **chip value** (5, 10, 25, 50, or 100 coins)
4. Fine-tune your wager with the **− / +** buttons
5. Press **✦ SPIN ✦** (or hit `Space` on desktop) to spin the wheel
6. Watch the wheel slow to a stop — win or lose based on where the ball lands
7. Collect winnings and go again — if you bust, your balance resets to 1,000 coins!

---

## 💰 Bet Types & Payouts

### Outside Bets (Even Chance — 1:1)

| Bet | Covers | Pays |
|-----|--------|------|
| Red | 18 red numbers | 1:1 |
| Black | 18 black numbers | 1:1 |
| Odd | 1,3,5…35 | 1:1 |
| Even | 2,4,6…36 | 1:1 |
| Low (1–18) | Numbers 1 to 18 | 1:1 |
| High (19–36) | Numbers 19 to 36 | 1:1 |

### Dozens & Columns (2:1)

| Bet | Covers | Pays |
|-----|--------|------|
| 1st Dozen | 1–12 | 2:1 |
| 2nd Dozen | 13–24 | 2:1 |
| 3rd Dozen | 25–36 | 2:1 |
| Column 1 | 1, 4, 7 … 34 | 2:1 |
| Column 2 | 2, 5, 8 … 35 | 2:1 |
| Column 3 | 3, 6, 9 … 36 | 2:1 |

### Straight Up & Special (35:1)

| Bet | Covers | Pays |
|-----|--------|------|
| Any Single Number | 1 specific pocket | 35:1 |
| Green (0) | The zero pocket | 35:1 |

> **House edge:** 2.7% — standard European single-zero roulette.  
> **Formula:** Payout = Bet × (Multiplier + 1)

---

## 🎯 Controls

### Desktop

| Input | Action |
|-------|--------|
| Click a bet tab | Switch between Outside / Dozens / Columns / Numbers |
| Click a bet button | Select your bet type |
| Click a chip (5–100) | Set chip denomination |
| `−` / `+` buttons | Adjust bet amount precisely |
| **SPIN** button | Spin the wheel |
| `Space` | Quick spin shortcut |
| `Esc` | Close any open modal |

### Mobile

| Input | Action |
|-------|--------|
| Tap bet tabs | Navigate bet categories |
| Tap bet button | Select bet type |
| Tap chip | Set chip value |
| Tap `−` / `+` | Adjust bet amount |
| Tap **SPIN** | Spin the wheel |

---

## ✨ Features

- **🎡 Authentic European Wheel** — 37-pocket single-zero wheel with the correct real-world number sequence drawn entirely on HTML5 Canvas
- **4 Bet Categories** — Outside Bets, Dozens, Columns, and Straight Up number bets
- **🎰 Casino Chip System** — 5 chip denominations (5 / 10 / 25 / 50 / 100) with fine +/− control
- **📊 Live Stats HUD** — Balance, Current Bet, Last Win/Loss, and Spin count always visible
- **🏆 Win / Result Modal** — Animated result overlay after every spin showing the landing number, colour, and payout
- **📜 History Strip** — Last 12 results shown as coloured balls (red / black / green)
- **ⓘ Info Modal** — Full how-to-play guide and payout table accessible at any time
- **Smooth Spin Animation** — Custom eased animation with 5–8 full wheel rotations before landing
- **📱 Fully Responsive** — Works on desktop, tablet, and mobile with no layout issues
- **♿ Keyboard Accessible** — `Space` to spin, `Esc` to close modals
- **🔄 Auto Reset** — Balance resets to 1,000 coins if you go bust
- **Zero Dependencies** — Pure HTML5 Canvas, CSS3, and vanilla JavaScript

---

## 🔧 Technical Implementation

### Wheel Rendering (HTML5 Canvas)

The roulette wheel is drawn programmatically on a `<canvas>` element every frame during the spin animation:

```javascript
// European wheel sequence — authentic pocket order
const WHEEL_SEQUENCE = [
  0,32,15,19,4,21,2,25,17,34,6,27,13,36,11,30,8,23,10,
  5,24,16,33,1,20,14,31,9,22,18,29,7,28,12,35,3,26
];
```

Each of the 37 segments is drawn using `ctx.arc()` with:
- **Segment fill** — correct red / black / green colour per number
- **Gold border strokes** — matching real wheel aesthetics
- **Rotated number labels** — each label rotates with its segment so it always reads radially

### Spin Animation & Landing Mathematics

The spin uses `requestAnimationFrame` with a **cubic ease-out** curve for a smooth, decelerating stop:

```javascript
// Ease out cubic — fast start, slow deceleration to stop
const eased = 1 - Math.pow(1 - progress, 3);
```

The target landing angle is calculated precisely so the winning pocket aligns with the pointer at the top:

```javascript
const segAngle   = 360 / 37;
const segCenter  = landingIndex * segAngle;
const extraSpins = 5 + Math.floor(Math.random() * 4); // 5–8 full rotations
const targetAngle = extraSpins * 360 + (360 - segCenter) + (segAngle / 2);
```

Wheel rotation state persists between spins so the wheel always continues from where it stopped — never resetting to zero.

### Win Evaluation Engine

A single `evaluateBet(num, betType)` function handles all bet type resolution:

```
Straight Up  → exact number match            → 35:1
Red / Black  → colour lookup array           → 1:1
Odd / Even   → num % 2 check (0 excluded)    → 1:1
Low / High   → range check 1–18 / 19–36      → 1:1
Dozen        → range check per dozen         → 2:1
Column       → num % 3 === column offset     → 2:1
```

### Responsive Layout

- CSS custom properties (`--gold`, `--felt`, etc.) for a consistent luxury theme throughout
- `clamp()` for fluid typography scaling between mobile and desktop
- Scrollable bet tab row with hidden scrollbar for small screens
- Bet option grid adapts from 3 columns to 2 on narrow viewports

---

## 📁 Project Structure

```
Royal-Roulette/
│
├── index.html      # Complete game — wheel canvas, betting UI, modals, game logic
│
└── (self-contained — no external assets required)
```

> The entire game is a single self-contained HTML file. All CSS and JavaScript are inline.

---

## 🚀 Getting Started

No build step, no package manager, no dependencies.

```bash
# Clone the repository
git clone https://github.com/tanmoy34/Royal-Roulette.git

# Open directly in your browser
cd Royal-Roulette
open index.html
```

Or visit the **[live demo](https://tanmoy34.github.io/)** — no setup required.

---

## 👤 Author

**Tanmoy Ghatak**  
Senior Game Developer — Unity · Unreal Engine · HTML5

- 🌐 Portfolio: [tanmoy34.github.io](https://tanmoy34.github.io/)
- 💼 LinkedIn: [linkedin.com/in/tanmoy-ghatak-b8707a14b](https://www.linkedin.com/in/tanmoy-ghatak-b8707a14b/)
- 📧 Email: tanmoyghatak1199@gmail.com

---

> *The wheel always turns. The question is whether you're ready when it stops.*
