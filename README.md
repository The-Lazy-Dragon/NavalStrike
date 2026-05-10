```
 _   _                 _ _____ _        _ _         
| \ | |               | /  ___| |      (_) |        
|  \| | __ ___   ____ | \ `--.| |_ _ __ _| | _____  
| . ` |/ _` \ \ / / _` |`--. \ __| '__| | |/ / _ \ 
| |\  | (_| |\ V / (_| /\__/ / |_| |  | |   <  __/ 
\_| \_/\__,_| \_/ \__,_\____/ \__|_|  |_|_|\_\___| 
```

# ⚓ NAVAL STRIKE v1.0.0

> **Tactical naval combat. No frameworks. No installs. One `.html` file.**

[![Made by The Lazy Dragon](https://img.shields.io/badge/Made%20by-The%20Lazy%20Dragon%20怠竜-ff153f?style=flat-square)](https://github.com/The-Lazy-Dragon)
[![Pure HTML](https://img.shields.io/badge/Stack-Pure%20HTML-00fff7?style=flat-square)](#)
[![No Framework](https://img.shields.io/badge/Framework-None%20Needed-3a486a?style=flat-square)](#)
[![Achievements](https://img.shields.io/badge/Achievements-35-712637?style=flat-square)](#-achievements)
[![Ships](https://img.shields.io/badge/Ships-25%20Classes-00fff7?style=flat-square)](#-fleet-manifest)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](LICENSE)

---

## 🎮 What is this?

It's Battleship. But neon. But futuristic. But with 10 combatants, 5 ambient music themes, smart AI with actual threat assessment, 35 achievements, a Konami code, a dev console, hidden easter eggs, and a procedural audio engine built entirely in the Web Audio API.

So yeah. Just Battleship.

---

## ▶ Play

> Download `naval_strike_v4.html` → open it in your browser → that's it.

No npm install. No build step. No webpack. No node_modules. No dependencies at all.

```bash
git clone https://github.com/The-Lazy-Dragon/naval-strike.git
cd naval-strike
# open naval_strike_v4.html in your browser
```

Or just download the raw HTML file directly.

---

## ✨ Features

### ⚔ Game Modes

| Mode | Description |
|---|---|
| **Player vs Player** | 2–10 human commanders, local pass-and-play |
| **Player vs AI** | 1–5 humans vs 1–5 AI admirals, mix freely |
| **AI Battle** | 2–10 AIs fight, you observe and analyse their tactics |

### 🗺 Grid Sizes

| Grid | Name | Feel |
|---|---|---|
| 10×10 | Tiny | Blink-and-it's-over |
| **15×15** | **Micro (default)** | **Fast, punchy** |
| 20×20 | Skirmish | Classic feel |
| 30×30 | Campaign | Extended battles |
| 40×40 | Warfare | Serious commitment |
| 50×50 | Devastation | You asked for this |

### 🚢 Fleet Manifest — 25 Ship Classes

**8 Default Ships** (always active):

| Ship | Size |
|---|---|
| Carrier | 6 |
| Battleship | 5 |
| Cruiser | 4 |
| Submarine | 4 |
| Destroyer | 3 |
| Gunboat | 3 |
| Patrol | 2 |
| Interceptor | 2 |

**17 Extra Ships** (opt-in via Settings → Enabled Ships):

| Ship | Size | Ship | Size |
|---|---|---|---|
| Dreadnought | 8 | Leviathan | 8 |
| Titan | 7 | Colossus | 7 |
| Warship | 6 | Galleon | 6 |
| Frigate | 5 | Flagship | 5 |
| Corvette | 4 | Minelayer | 4 |
| Monitor | 4 | Torpedo Boat | 3 |
| Gunship | 3 | Raider | 3 |
| Stealth Sub | 3 | Scout | 2 |
| Skiff | 2 | | |

### 🤖 AI System — 3 Difficulty Tiers

Each AI has its own name, personality, and tactical logic:

| AI | Name | Behaviour |
|---|---|---|
| **Easy** | DELTA | Random shots. No tactical awareness. Punching bag. |
| **Normal** | ALPHA | Hunts adjacent cells after a hit. Targets weakest enemy. 70/30 random mix to stay unpredictable. |
| **Hard** | EAGLE / TITAN | Full threat scoring: wounds, momentum, coordination. Collinear ship extension. Checkerboard sweep. Actively avoids piling on already-doomed targets. Reads global hit data in multi-player. |

**Multi-target threat scoring (Hard AI):**
- Prefers enemies it's already wounding (finish what you started)
- Penalised for ganging up when 2+ AIs already swarm the same target
- Bonus for coordinated finishing strikes
- Reads hits made by ALL players, not just itself (hard mode global intelligence)

### 🎵 Audio Engine — Procedural, No Files

All music and sound effects are synthesized live using the **Web Audio API**. No audio files. No recordings. No samples. Everything is built from oscillators, noise buffers, and filters.

*i just tried my best to do with what i had ;)*

**5 Ambient Themes:**

| Theme | Sound | Lock |
|---|---|---|
| 🌊 Cosy Ocean | Waves, pentatonic melody, wind chimes | Always available |
| 🥁 War Drums | Naval percussion, cannon booms, brass fanfare | Always available |
| 🌆 Cyberpunk | Detuned sawtooth pad, 16th-note arpeggio, hi-hat grid | Always available |
| 💻 Hacker/Glitch | Corrupted drone, data ticks, error bursts, scan sweep | 🔒 Unlock Konami Code |
| ⛩ Ancient/Feudal | Temple gong, taiko drums, koto plucks, shakuhachi flute | 🔒 Unlock Tearyu Easter Egg |

**SFX:** Hit (thump + noise burst), Miss (hollow sine), Sunk (3-layer boom + ping), Win (ascending chime), Click (button feedback).

---

## ⚙ Settings

### Colors
Full RGB color picker for every UI element: background, panels, accent, danger, midtone, ship color.

### Gameplay
- Grid size (10×10 to 50×50)
- AI delay (0–3000ms)
- Transition countdown timer (2–15s)
- Global shot visibility toggle (see all players' shots or just your own)
- Particle toggle

### Performance Sliders
Tune each performance-heavy system independently:

| Slider | Default | Effect |
|---|---|---|
| Particle Count | 40 | More = prettier, more CPU |
| Particle FPS | 30 | Higher = smoother, more CPU |
| Trail Frequency | 40ms | Lower = more trail dots, more CPU |
| Matrix Rain FPS | 20 | Higher = faster rain, more CPU |

> ⚠ Backdrop-filter blur and CSS cell transitions have been permanently removed — they caused the most lag and weren't worth the trade-off.

### FPS Counter
Toggle in Settings → Gameplay. Shows live FPS in the nav bar with a colour-coded bar: green ≥50, yellow ≥30, red <30. Averages last 20 frames.

### Ambient Theme Selector
Switch themes live. Locked themes show a padlock and the unlock condition.

### Ship Toggles
Enable or disable any of the 25 ships. Minimum 4 ships required. Extra ships must be opted in first, then can be toggled on/off.

---

## 🏆 Achievements

35 total. Some are visible from the start, some are hidden and only reveal themselves when triggered.

### Progression
| Achievement | Condition |
|---|---|
| First Blood | Complete your first battle |
| Veteran | Play 10 games |
| Commander | Play 50 games |
| Admiral | Play 100 games |
| Fleet Marshal | Play 250 games |
| War Veteran | Play 500 games |
| Naval Legend | Play 1000 games |
| Eternal Admiral | Play 1250 games |

### Wins
| Achievement | Condition |
|---|---|
| First Salvo | Win your first battle |
| Sharp Shooter | Win 10 battles |
| Destroyer | Win 50 battles |
| Fleet Hunter | Win 100 battles |
| Leviathan | Win 500 battles |
| God of War *(hidden)* | Win 1000 battles |

### AI Combat
| Achievement | Condition |
|---|---|
| Delta's Nemesis | Defeat Easy AI 10 times |
| Alpha Bane | Defeat Normal AI 25 times |
| Eagle Slayer | Defeat Hard AI 10 times |
| Shadow Destroyer | Defeat Hard AI 100 times |
| Machine Wars | Play 100 AI games |
| Crucible Forged | Play 50 hard-AI games |
| Born in Fire | Play 100 hard-AI games |

### Special
| Achievement | Condition |
|---|---|
| Local Legend | Play 10 PvP games |
| The Observer | Watch 5 AI battles |
| War of Nations | Play a 5+ combatant battle |
| Grand War | Play a full 10-combatant battle |
| Matrix Protocol | Activate the Konami Code |
| Ghost in the Machine | Open and use the dev console |
| Total Annihilation | Sink every enemy ship in one battle |
| Lazy Admiral | Use Auto Deploy |
| Second Thoughts | Undeploy a ship during placement |
| Lone Survivor *(hidden)* | Outlast all other human players |
| Flash Strike *(hidden)* | Win in under 30 turns |
| War of Attrition *(hidden)* | Play a game over 500 turns |

<details>
<summary>

### Easter Eggs *(all hidden)*

</summary>

| Achievement | How to unlock |
|---|---|
| The Lazy Dragon Awakens | Name a player `怠竜 TEARYŪ`, `TEARYŪ`, or `THE LAZY DRAGON` |
| Oasis Commander | Name a player `PARZIVAL`, `WADE WATTS`, `ART3MIS`, `AECH`, or `HALLIDAY` |
| Red Devils Navy | Name a player `ROONEY`, `FERGIE`, `CANTONA`, `RED DEVIL`, `SOLSKJAER`, etc. |
| Sixth Man | Name a player `JORDAN`, `PIPPEN`, `RODMAN`, `CHICAGO BULL`, etc. |
| The Chosen Admiral | Name a player `LEBRON`, `KING JAMES`, `THE CHOSEN ONE`, `LBJ`, etc. |
| Dragon's Bane *(???)*  | Unlock dev mode and manipulate stats |

</details>

---

## 🕹 Konami Code

```
↑ ↑ ↓ ↓ ← → ← → B A
```

Activates binary matrix rain background + full neon green mode. Toggleable — hit it again to turn it off. Also unlocks the **Hacker/Glitch** ambient theme and the **Matrix Protocol** achievement.

---

## 💻 Dev Console

Press **`~`** to open the built-in terminal.

### Available Commands

| Command | Example | What it does |
|---|---|---|
| `help` | `help` | List all commands |
| `stats` | `stats` | Print all win/loss records |
| `reset-stats` | `reset-stats` | Factory reset everything to 0 |
| `reset-player` | `reset-player COMMANDER 1` | Zero out one player's record |
| `reset-ai` | `reset-ai hard` | Zero out an AI difficulty tier |
| `wins` | `wins COMMANDER 1` | View a player's win count |
| `achievements` | `achievements` | List all unlocked achievement IDs |
| `unlock` | `unlock konami` | Force-unlock any achievement by ID |
| `konami` | `konami on` / `konami off` | Toggle matrix mode |
| `export` | `export` | Download stats as `.txt` |
| `clear` | `clear` | Clear console output |
| `version` | `version` | Show version |

### Dev Mode (stat manipulation)
Stat manipulation is locked behind a hidden sequence. If you know, you know. The console will guide you.

> The `Dragon's Bane` achievement unlocks automatically once dev mode is activated.

---
<details>
<summary>

## 🐉 Easter Eggs -spoiler

</summary>

### Tearyu Mode
Name any player **`怠竜 TEARYŪ`**, **`TEARYŪ`**, **`THE LAZY DRAGON`**, or any variation (underscores, hyphens, lowercase all work). The entire game shifts to a crimson blood-red palette using `#FF0000 · #BF0000 · #800000 · #400000 · #000000`. Also unlocks the **Ancient/Feudal** ambient theme.

### Ready Player One
Name a player after a character from the OASIS: `PARZIVAL`, `WADE WATTS`, `ART3MIS`, `AECH`, `HALLIDAY`, `DAITO`, or `SHOTO`.

### Man United
Name a player after a Red Devil legend: `ROONEY`, `FERGIE`, `CANTONA`, `GIGGS`, `SCHOLES`, `BECKHAM`, `RED DEVIL`, `SOLSKJAER`, etc.

### Chicago Bulls
Name a player after a Bulls legend: `JORDAN`, `PIPPEN`, `RODMAN`, `CHICAGO BULL`, `DERRICK ROSE`, etc.

### LeBron
Name a player `LEBRON`, `KING JAMES`, `THE CHOSEN ONE`, `LBJ`, `AKRON HAMMER`, etc.
</details>

---

## 🛸 Local Multiplayer

Naval Strike supports **local pass-and-play** multiplayer out of the box. When it's a human player's turn, a countdown screen appears (duration configurable in settings) so they can pass the device without seeing the other player's fleet.

**LAN/WiFi multiplayer** requires a tiny local server since browsers block file:// cross-origin requests. Simplest approach:

```bash
# Python 3
python3 -m http.server 8080

# Then on any device on the same WiFi:
# http://<your-local-ip>:8080/naval_strike_v4.html
```

Full real-time sync via WebSockets is planned for a future update.

---

## 🎨 Color Palette

| Role | Hex |
|---|---|
| Background | `#182433` |
| Panel | `#1e2e42` |
| Accent (Cyan) | `#00fff7` |
| Danger (Red) | `#ff153f` |
| Dark Red | `#712637` |
| Midtone | `#3a486a` |
| Text | `#c8e6f0` |

---

## 📂 Project Structure

```
naval-strike/
└── naval_strike_v4.html    # The entire game. One file. That's it.
```

No build tools. No package.json. No node_modules. Just open the file.

---

## 🔧 Performance Notes

The game is designed to run well on most devices but has configurable performance options in Settings → Performance:

- **Particles** are throttled to 30fps by default (adjustable)
- **Matrix rain** runs at 20fps (adjustable)
- **Cursor trail** spawns every 40ms (adjustable)
- Grid cells are diff-patched rather than rebuilt from scratch each turn
- AI turns have a minimum 16ms gap to keep the browser breathing

---

## 📊 Stats & Export

All stats are saved to `localStorage` and survive page reloads. Export to a `.txt` file anytime via Settings or the console command `export`. Import it back with the Import button.

Tracked per-player and per-AI-difficulty: wins, losses, games played, win rate.

---

## 🌐 Play Online

Its live at:
```
https://the-lazy-dragon.github.io/savingitforlater.com
```
***Try it ;)***

---

## 🧩 About the Dev

**The Lazy Dragon** · `怠竜 Tearyū`

BSc IT student who builds things way more complex than they need to be and calls it a game. Buils shi at 3am because there was nothing else to do and sleep was a suggestion.

- GitHub: [@The-Lazy-Dragon](https://github.com/The-Lazy-Dragon)
- Discord: `this.isnt.craig_`
- Reddit: `u/Red_DevilAS07`

### Also check out:
**[Lazy Dragon's TicTacToe](https://github.com/The-Lazy-Dragon/lazy-dragons-tictactoe)** — The predecessor. Same DNA: neon aesthetic, achievements, Konami code, dev console, stat tracking, all in one `.html` file. Play it live at [the-lazy-dragon.github.io/lazy-dragons-tictactoe](https://the-lazy-dragon.github.io/lazy-dragons-tictactoe/tictactoe.html).

---

## 📄 License

MIT — do whatever you want with it.

---

*Built with zero frameworks and questionable life choices — actually built this one at 4am because I had nothing to do after going thru 12 straight defeats in Mobile Legends and couldn't sleep. lol*

**⭐ Star the repo if the Konami code made you smile**