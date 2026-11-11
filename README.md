# NDSWeb 🎮✨

Play Nintendo DS, Game Boy Advance, Game Boy, NES, SNES, Game Gear, and Atari 2600 games right inside your browser. No installs, no accounts, no backend. Drop your ROMs in and start playing, then invite a friend to watch (or play along) over a peer-to-peer connection.

🌐 **Live:** [codymkw.github.io/ndsweb](https://codymkw.github.io/ndsweb)

---

## What is this?

**NDSWeb** is a single-file web launcher built on **[EmulatorJS](https://emulatorjs.org/)**. It has a dashboard, a searchable game library, automatic save syncing, a save manager, themes, and a peer-to-peer **Connect** tab for watching friends play. Your ROMs and saves live in your browser's IndexedDB and are never uploaded to a server.

### Supported systems & formats

| System | Extensions | Core |
| --- | --- | --- |
| Nintendo DS | `.nds` | melonDS |
| Game Boy Advance | `.gba` | mGBA |
| Game Boy / Game Boy Color | `.gb`, `.gbc` | Gambatte |
| NES | `.nes` | FCEUmm |
| SNES | `.sfc` | Snes9x |
| Sega Game Gear | `.gg` | Genesis Plus GX |
| Atari 2600 | `.a26` | Stella |

---

## ✨ Features

### Playing
* **Drag & drop** a ROM onto the dashboard (or use the file picker), or launch anything from your library.
* **Game Library** with search and sorting by recently played, date added, name, or file size.
* **In-game toolbar** with quit, save state, load state, download or import a `.sav`, chat, friends, **rotate screen** (handy for games that play sideways), pin toolbar, and fullscreen.
* **Optional BIOS support** for systems that benefit from it. (NDS BIOS is imported from inside the emulator menu.)

### Saves
* **Auto-syncing saves:** your game's real save data is mirrored into IndexedDB every few seconds and restored when you launch the game again.
* **Save Manager** (Settings): see every game save and save state stored in the browser, filter them, **rename** them, or **delete** individual ones. Renaming only changes the label shown in the manager, so the game still finds its save.
* **Export / import** raw `.sav` files, or back up your whole library's saves (labels included) as a JSON file.
* **Local Storage meter** shows how much browser storage you're using.
* **Export / Import Library** (Settings): back your games up as `.zip` files (split into ~1.5 GB parts for big libraries, with custom covers and dates included) and restore them in another browser. Import also accepts loose ROM files or ordinary `.zip` archives of ROMs, and skips games you already have. BIOS files and saves are not included (use Export Saves for saves).
* Atari 2600 games have no battery saves, so they won't appear in the Save Manager.

### Connect (peer-to-peer, via PeerJS)
* **Friends:** share your ID or invite link; the other person accepts, and you're both saved as friends and reconnect automatically when you're online together.
* **Watch live:** accepted friends can watch your game as a live stream, with an "N watching" badge in your toolbar. Screen rotation carries over to watchers.
* **Player 2:** for 2-player NES / SNES games, a watching friend can send their controller to you and play as Player 2.
* **Library compare:** friends can compare game titles with each other. Only titles and consoles are shared.
* **Copy a game:** optionally let friends copy a game file from your library (**Allow / Ask me / Off**). Saves are never sent.
* **Chat** with connected friends, from the Connect tab or in-game.
* Watching, Player 2, library sharing, and game copying each have their own on/off setting.

### Discord Rich Presence
Connect Discord in Settings and your profile shows the game you're playing, with its cover art when available. When you're watching a friend instead, that shows too (with or without their display name, your choice). Presence needs only Discord's presence permission; a small Cloudflare Worker handles the OAuth token exchange and cover-art assets.

### Themes
Pick your own accent color, switch between background styles (Clean, Retro Grid, Scanlines), toggle ambient glow, or switch to a monospace retro font.

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
| **Fullscreen** | `F11` |
| **Quit** | `Escape` |

---

## 🚀 Running Locally

NDSWeb is a static web app, so there's no build step and no Node backend.

1. Clone or download the repository.
2. Serve the folder with any static server and open it in your browser:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

The Discord presence feature needs the `ndsweb-helper` Cloudflare Worker and a registered Discord app, so it won't work in a bare local copy.

---

## 🛠️ Under the Hood

Built with plain web standards and no frontend framework:

* **HTML5 / CSS3** with CSS variables for theming.
* **Vanilla JavaScript** for the UI, state, and file management, all in a single `index.html`.
* **IndexedDB** for local ROM, BIOS, and save storage.
* **[EmulatorJS](https://emulatorjs.org/)** loaded from the EmulatorJS CDN as the emulation engine.
* **[PeerJS](https://peerjs.com/)** for peer-to-peer connections (friends, watching, Player 2, chat, library sharing).
* **[Lucide](https://lucide.dev/)** for icons.
* **Cloudflare Worker** (`ndsweb-helper`) for Discord OAuth and cover-art assets only.

---

## ⚖️ ROMs

NDSWeb doesn't include or download any games. Only use ROMs and BIOS files you legally own.
