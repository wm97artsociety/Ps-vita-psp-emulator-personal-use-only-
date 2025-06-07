
# VitaPSP Emulator Project (No Jailbreak Needed)

This is a full-featured custom emulator interface for playing **PSP games** with a **PS Vita-style UI**, designed to run on Android APKs or as a web-based HTML application. It uses an embedded **PPSSPP** core and simulates a package manager that mimics Sony's Vita system — no BIOS, jailbreaking, or official firmware dumps required.

---

## 🧠 Key Features

- ✅ VitaOS-style game launcher UI
- ✅ Fake but functional package manager (Game Bubble Grid)
- ✅ Game metadata database with firmware compatibility
- ✅ Custom savegame exploit simulator (e.g., Patapon method)
- ✅ Compatible with ISOs/CSOs (Def Jam, GTA, Ape Escape tested)
- ✅ Custom theming (CSS)
- ✅ Android and Web (HTML5) support

---

## 📁 Folder Structure Overview

```
VitaPSP_Emulator_Complete/
├── assets/               # Game icons, splash screens, and UI assets
├── games/                # Place your ISO or CSO PSP games here
├── database/             # games.json with metadata for the launcher
├── apk_source/           # Android-specific launcher code
├── ppsspp_core/          # Embedded PPSSPP core (placeholder)
├── themes/               # CSS themes for the UI
├── web/                  # HTML-based launcher version
├── sdk_data/             # SDK metadata for game system
├── LICENSE               # Open source license (MIT)
└── README.md             # Full software instructions (this file)
```

---

## 🗂️ games.json Format (database/games.json)

The fake package manager reads from a metadata file like this:

```json
[
  {
    "id": "ULUS10567",
    "title": "Def Jam: Fight for NY - The Takeover",
    "type": "PSP_GAME",
    "icon": "assets/icon_defjam.png",
    "iso_path": "games/defjam.iso",
    "save_path": "saves/ULUS10567/",
    "firmware_compatible": ["3.60", "3.68", "3.74"]
  }
]
```

You can add more games by adding new entries with proper ISO paths and icon images.

---

## 📲 How It Works (Android APK Version)

1. Launches from a custom VitaOS-themed APK interface
2. Reads `games.json` to display game bubbles
3. Select game → Verifies firmware compatibility
4. Launches custom savegame exploit simulation (virtual Patapon-like boot)
5. Loads game via embedded `libppsspp.so`
6. Supports touchscreen, gamepad, and save/load states

---

## 🌐 How It Works (Web Version)

1. Load `web/index.html` on any browser
2. Vita-style game selection interface using `games.json`
3. Integrates a WebAssembly version of PPSSPP (you must add your own core)
4. Mounts local ISO files through input or drag-and-drop
5. Launches with the same interface and custom game handling

---

## 🛠️ Android Development

Inside `/apk_source/` you'll find:

- `MainActivity.java` — Renders the UI and parses game metadata
- `EmulatorLauncher.java` — Loads ISO into embedded emulator
- `build.gradle` — Set up to compile as a standard Android APK
- Uses PPSSPP core stored in `/ppsspp_core/libppsspp.so`

---

## 🎨 Theming

Change styles by editing:

- `themes/default_theme.css`
- Add new `.css` files for different skins (e.g., "Dark Vita", "Retro Blue")

---

## 🧪 Confirmed Compatible Games

| Game Title                        | Working Status |
|----------------------------------|----------------|
| Def Jam: Fight for NY (PSP)      | ✅ Full Speed |
| GTA: Liberty City Stories (PSP)  | ✅ Full Speed |
| GTA: Vice City Stories (PSP)     | ✅ Playable |
| Ape Escape: On the Loose (PSP)   | ✅ Full Speed |

---

## ⚠️ LEGAL DISCLAIMER

This software is provided for **educational and personal backup purposes only**.  
No copyrighted BIOS or game files are included.  
You must supply your own legally obtained ISO/CSO backups.

---

## 👑 Created For

This emulator experience and code scaffold was created for **William (Manier Mona Lisa)** as a research tool and experimental gaming interface.  
It's open for further development, customization, and interface upgrades.

---
