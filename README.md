Here is a casual, human-written `README.md` tailored for your GitHub repository. It hits all the right features from your code while keeping that chill, developer-to-developer vibe.

---

# NDSWeb 🎮✨

Play your favorite Nintendo DS, Game Boy Advance, Game Boy, and Game Boy Color games right inside your browser. No extra setup or complicated software needed—just drop your ROMs in and start playing.

🌐 **Live Demo:** [https://codymkw.github.io/ndsweb](https://codymkw.github.io/ndsweb)

---

## What is this?

**NDSWeb** is a clean, modern web-based retro game launcher and emulator powered by **EmulatorJS**. It features a slick dashboard, automatic save sync, custom themes, and full local storage support so your games and saves stay completely private in your browser.

### Supported Systems & Formats

* **Nintendo DS (`.nds`)** — Powered by melonDS
* **Game Boy Advance (`.gba`)** — Powered by mGBA
* **Game Boy / Game Boy Color (`.gb`, `.gbc`)** — Powered by Gambatte

---

## ✨ Features

* **Auto-Syncing Saves:** NDSWeb mirrors your game's real save data (`.sav`) into your browser's IndexedDB every few seconds and restores it automatically when you launch.
* **Save & State Management:** Easily export/import raw `.sav` files or back up your entire library's progress as a JSON file via the Settings menu.
* **Custom Themes & Accents:** Pick your own accent color, switch between background styles (Clean, Retro Grid, Scanlines), toggle ambient glow, or switch to a monospace retro font.
* **Optional BIOS Support:** Upload official GBA, GB, and GBC BIOS files to boost emulation accuracy.
* **Fully Responsive:** Looks and plays great on desktop and mobile browsers alike, complete with customizable keyboard shortcuts.

---

## ⌨️ Controls & Shortcuts

| Action | Shortcut |
| --- | --- |
| **A Button** | `Z` |
| **B Button** | `X` |
| **X Button** | `A` |
| **Y Button** | `S` |
| **L / R Shoulders** | `Q` / `E` |
| **Start / Select** | `Enter` / `Shift` |
| **Fullscreen / Quit** | `F11` / `Escape` |

---

## 🚀 Running Locally

Since NDSWeb is a static web app, you don't need any complex build steps or Node backends to run it.

1. Clone or download the repository.
2. Open `index.html` in your favorite browser, or serve it using a simple local server (like Python's `http.server` or a Live Server extension).

```bash
python3 -m http.server 8000

```

---

## 🛠️ Under the Hood

Built with plain web standards—no heavy frontend frameworks required:

* **HTML5 / CSS3** with CSS Variables for dynamic theming.
* **Vanilla JavaScript** handling the UI, state, and file management.
* **IndexedDB** for local ROM, BIOS, and save storage.
* **EmulatorJS** core engine handling the heavy lifting.
