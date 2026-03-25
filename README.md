# ⚒ ForgeWoW Database
The definitive, fan-built World of Warcraft item database.  
Powered by the official Blizzard Battle.net API · Free · No account required · Updated daily

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

## 🌐 Live Site
- **Main Site:** ForgeWoWdatabase.com  
- **Sister Site:** WoWHousingDecor.com — All your WoW Player Housing needs

---

## 📖 About
ForgeWoW Database is a fan-made, community-driven World of Warcraft encyclopedia covering:

- 2.4M+ items — weapons, armor, consumables, mounts, pets, toys, housing
- 500k+ spells and abilities across all classes
- 300k+ quests with objectives, rewards, and zone context
- 200k+ NPCs — bosses, vendors, quest givers, and lore characters
- All expansions — Classic through The War Within (11.x)

Built entirely with vanilla HTML, CSS, and JavaScript. No frameworks. No build tools. No database server.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔍 Advanced Search | Search by name, item ID, quality, item level, class, slot, and expansion |
| 🧊 3D Item Previews | Interactive Three.js 3D model viewer — drag to rotate |
| 🎨 Quality Color Coding | Poor · Common · Uncommon · Rare · Epic · Legendary · Artifact |
| 🗺️ Zone Maps | Interactive maps for every zone |
| 🏆 BiS Lists | Best in Slot recommendations for every class and spec |
| ✨ Transmog Finder | Browse collectible appearances by slot, armor type, and source |
| 📖 Lore Guides | Deep-dive articles and full Azeroth historical timeline |
| ⚒ Professions | All 12 professions with recipes, demand ratings, and leveling info |
| 📜 Quest Database | Daily, Epic, Dungeon, Raid, and World quests with full reward listings |
| 👥 NPC Database | Bosses, vendors, trainers, and key lore characters |
| 🏠 Housing Items | Full WoW Player Housing catalogue |
| 📱 Responsive | Fully mobile-friendly layout |

---

## 🗂 Project Structure

```
forgewow/
│
├── index.html              # Home page
├── items.html              # Full item browser
├── weapons.html            # Weapons by type
├── armor.html              # Armor by type and slot
├── spells.html             # Spells & abilities
├── quests.html             # Quest database
├── npcs.html               # NPC browser
├── professions.html        # All 12 professions
├── lore.html               # Lore articles
├── maps.html               # Zone maps
├── search.html             # Advanced search
├── bis.html                # Best in Slot lists
├── transmog.html           # Transmog browser
├── about.html              # About page
├── contact.html            # Contact form
│
├── forge-assets.js         # Shared brand assets
│
└── data/                   # Optional local JSON files
    ├── weapons.json
    ├── armor.json
    ├── consumables.json
    ├── mounts.json
    ├── pets.json
    ├── toys.json
    ├── housing.json
    └── fish.json
```

---

## 🚀 Getting Started

### Option 1 — Open Locally
```bash
git clone https://github.com/dmcdelite/ForgeWow.git
cd ForgeWow
# Open index.html in any modern browser
```

### Option 2 — Deploy to a Web Host
Upload all files to `public_html/` — no server-side code required.

---

## 🔑 Blizzard Battle.net API Setup

### 1. Create a Free API Client
1. Go to [develop.battle.net](https://develop.battle.net) and log in
2. Click **Create Client**
3. Give it any name (e.g. `ForgeWoW`)
4. Set redirect URL to `https://localhost`
5. Copy your **Client ID** and **Client Secret**

> ⚠️ **Never commit your Client ID or Client Secret to this repository.**  
> Store them only in your browser session or a local `.env` file that is `.gitignore`d.

### 2. Connect in the Browser
Open `items.html`, click the **Battle.net** button, and enter your credentials in the setup modal.

**Security:** Credentials are stored only in the current browser session (memory only). Never saved to localStorage. Never sent to any third-party server.

### 3. Supported Regions

| Region | Value | Covers |
|---|---|---|
| US | `us` | Americas |
| EU | `eu` | Europe |
| KR | `kr` | Korea |
| TW | `tw` | Taiwan |

### API Endpoints Used
```
POST  https://{region}.battle.net/oauth/token
GET   https://{region}.api.blizzard.com/data/wow/item/{id}
GET   https://{region}.api.blizzard.com/data/wow/media/item/{id}
```

---

## 📦 Local Data Files (Offline Mode)

```json
[
  {
    "id": 19019,
    "name": "Thunderfury, Blessed Blade of the Windseeker",
    "quality": "Legendary",
    "level": 80,
    "itemClass": "Weapon",
    "itemSubClass": "Sword",
    "sellPrice": 1234500,
    "description": "Item flavour text here",
    "icon": "https://render.worldofwarcraft.com/us/icons/56/inv_sword_2h.jpg"
  }
]
```

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Markup | Vanilla HTML5 |
| Styles | Vanilla CSS3 |
| Scripts | Vanilla JavaScript (ES6+) |
| 3D Rendering | Three.js r128 |
| Fonts | Google Fonts |
| Data | Blizzard Battle.net API (OAuth 2.0) |
| Hosting | Any static web host |

---

## 🤝 Contributing

1. Fork the repository
2. Create a branch — `git checkout -b feature/your-feature-name`
3. Make your changes
4. Test by opening `index.html` in a browser
5. Submit a Pull Request

---

## 📄 License
MIT License — see [LICENSE](LICENSE) for details.

---

## ⚠️ Disclaimer
World of Warcraft® and Blizzard Entertainment® are registered trademarks of Blizzard Entertainment, Inc.  
ForgeWoW Database is an independent, fan-made project not affiliated with Blizzard Entertainment.

---

## 🔗 Links
- [Live Site](https://forgewowdatabase.com)
- [Sister Site](https://wowhousingdecor.com)
- [Blizzard API Docs](https://develop.battle.net)

---
⚒ *Forged by the community, for the community* ⚒
