# ⚒ ForgeWoW Database

> **The definitive, fan-built World of Warcraft item database.**  
> Powered by the official Blizzard Battle.net API · Free · No account required · Updated daily

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Pages](https://img.shields.io/badge/Pages-16-blue.svg)](#pages)
[![API](https://img.shields.io/badge/API-Blizzard%20Battle.net-blue.svg)](https://develop.battle.net/)
[![Sister Site](https://img.shields.io/badge/Sister%20Site-WoWHousingDecor.com-cyan.svg)](https://www.wowhousingdecor.com)

---

## 🌐 Live Site

**[ForgeWoWdatabase.com](https://forgewowdatabase.com)**  
Sister site: **[WoWHousingDecor.com](https://www.wowhousingdecor.com)** — All your WoW Player Housing needs

---

## 📖 About

ForgeWoW Database is a fan-made, community-driven World of Warcraft encyclopedia covering:

- **2.4M+ items** — weapons, armor, consumables, mounts, pets, toys, housing
- **500k+ spells** and abilities across all classes
- **300k+ quests** with objectives, rewards, and zone context
- **200k+ NPCs** — bosses, vendors, quest givers, and lore characters
- **All expansions** — Classic through The War Within (11.x)

Built entirely with vanilla HTML, CSS, and JavaScript. No frameworks. No build tools. No database server. Powered by the [Blizzard Battle.net API](https://develop.battle.net/) for live, accurate item data.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🔍 **Advanced Search** | Search by name, item ID, quality, item level, class, slot, and expansion |
| 🧊 **3D Item Previews** | Interactive Three.js 3D model on every item hover tooltip — drag to rotate in full detail view |
| 🎨 **Quality Color Coding** | Poor · Common · Uncommon · Rare · Epic · Legendary · Artifact color system |
| 🗺️ **Zone Maps** | Interactive maps for every zone — quest givers, boss spawns, resource nodes |
| 🏆 **BiS Lists** | Best in Slot recommendations for every class and spec |
| ✨ **Transmog Finder** | Browse collectible appearances by slot, armor type, and source |
| 📖 **Lore Guides** | Deep-dive articles and full Azeroth historical timeline |
| ⚒ **Professions** | All 12 professions with recipes, demand ratings, and leveling info |
| 📜 **Quest Database** | Daily, Epic, Dungeon, Raid, and World quests with full reward listings |
| 👥 **NPC Database** | Bosses, vendors, trainers, and key lore characters |
| 🏠 **Housing Items** | Full WoW Player Housing catalogue (see also WoWHousingDecor.com) |
| 📱 **Responsive** | Fully mobile-friendly layout |

---

## 🗂 Project Structure

```
forgewow/
│
├── index.html              # Home page (SEO-rich, sister site section, FAQ)
├── items.html              # Full item browser — all categories, sidebar filters
├── weapons.html            # Weapons by type (Sword/Axe/Mace/Dagger/Staff/Bow)
├── armor.html              # Armor by type (Plate/Mail/Leather/Cloth) and slot
├── spells.html             # Spells & abilities by magic school
├── quests.html             # Quest database by type and expansion
├── npcs.html               # NPC browser by type and faction
├── professions.html        # All 12 professions with recipes and guides
├── lore.html               # Lore articles and Azeroth historical timeline
├── maps.html               # Zone maps for all expansions
├── search.html             # Advanced cross-database search
├── bis.html                # Best in Slot lists by class
├── transmog.html           # Transmogrification appearance browser
├── about.html              # About page and disclaimer
├── contact.html            # Contact form
│
├── forge-assets.js         # Shared brand assets (logo, backgrounds, icons, button)
│                           # ⚠ Load this on every page — it injects all images via data URIs
│
└── data/                   # (Optional) Local JSON item data files
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

### Option 1 — Open Locally (No Server Needed)

1. Download or clone this repository
2. Place all files in the same folder
3. Open `index.html` in any modern browser
4. That's it — no build step, no npm install, no server required

```bash
git clone https://github.com/dmcdelite/ForgeWow.git
cd ForgeWow
open index.html   # macOS
# or double-click index.html on Windows
```

### Option 2 — Deploy to a Web Host

Upload all files to your hosting provider's public directory (e.g. `public_html/`). No server-side code required — it's all static HTML.

```
public_html/
  ├── index.html
  ├── items.html
  ├── forge-assets.js
  ├── ... (all other .html files)
  └── data/
      └── weapons.json (etc.)
```

---

## 🔑 Blizzard Battle.net API Setup

ForgeWoW pulls live item data directly from Blizzard's official API. To enable this:

### 1. Create a Free API Client

1. Go to [develop.battle.net](https://develop.battle.net/) and log in with your Blizzard account
2. Click **Create Client**
3. Give it any name (e.g. `ForgeWoW`)
4. Set the redirect URL to `https://localhost`
5. Copy your **Client ID** and **Client Secret**

### 2. Connect in the Browser

When you open `items.html` or `forgeWOWdatabase.html`, click the **Battle.net** button in the top nav. Enter your Client ID and Secret in the setup modal.

> **Security note:** Your credentials are stored only in the current browser session (memory only). They are never saved to `localStorage`, never sent to any third-party server, and only transmitted directly to `battle.net` for OAuth token exchange.

### 3. Supported Regions

| Region | Value | Covers |
|---|---|---|
| US | `us` | Americas |
| EU | `eu` | Europe |
| KR | `kr` | Korea |
| TW | `tw` | Taiwan |

### API Endpoints Used

```
POST  https://{region}.battle.net/oauth/token        → Get access token
GET   https://{region}.api.blizzard.com/data/wow/item/{id}         → Item data
GET   https://{region}.api.blizzard.com/data/wow/media/item/{id}   → Item icon
```

---

## 📦 Local Data Files (Offline Mode)

If you don't want to use the API, you can supply local JSON files in a `data/` folder. Each file should be an array of item objects:

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
    "icon": "https://render.worldofwarcraft.com/us/icons/56/inv_sword_2h_artifactskulloc_d_01.jpg"
  }
]
```

### Supported Item Fields

| Field | Type | Description |
|---|---|---|
| `id` | `number` | Blizzard item ID (required) |
| `name` | `string` | Item name |
| `quality` | `string` | Poor / Common / Uncommon / Rare / Epic / Legendary / Artifact |
| `level` | `number` | Item level (ilvl) |
| `requiredLevel` | `number` | Required character level |
| `itemClass` | `string` | Weapon / Armor / Consumable / Mount / etc. |
| `itemSubClass` | `string` | Sword / Plate / Flask / etc. |
| `inventoryType` | `string` | Head / Chest / Main Hand / etc. |
| `sellPrice` | `number` | Sell price in copper |
| `description` | `string` | Flavour text |
| `icon` | `string` | URL to item icon image |
| `location` | `string` | Where it drops / is obtained |
| `weightLbs` | `number` | Fish weight (fishing category) |
| `lengthIn` | `number` | Fish length (fishing category) |

---

## 🧊 3D Item Model System

ForgeWoW uses [Three.js](https://threejs.org/) (r128) to render procedural 3D item models in tooltips and the detail modal.

> **Note:** Blizzard's actual `.m2` game model files are not publicly accessible via their API. ForgeWoW generates procedural Three.js models based on item type and quality color. If Blizzard ever exposes model endpoints, the system is ready to swap them in.

### Shape Detection

The engine auto-detects item shape from the item name and subclass:

| Shape | Detected From |
|---|---|
| Sword | name contains `sword/blade/sabre` or subclass is `Sword` |
| Axe | name contains `axe/hatchet/chopper` or subclass is `Axe` |
| Mace | name contains `mace/hammer/maul` or subclass is `Mace` |
| Dagger | name contains `dagger/knife/shiv` |
| Staff | name contains `staff/stave/wand` |
| Bow | name contains `bow/crossbow/gun` |
| Shield | name contains `shield/bulwark/aegis` |
| Helm | name contains `helm/crown/cowl/hood` |
| Ring | name contains `ring/band/signet` |
| Potion | name contains `potion/flask/elixir` |
| Orb | fallback for trinkets, misc items |

### Quality Colors

| Quality | Hex Color |
|---|---|
| Poor | `#9d9d9d` |
| Common | `#c8c8c8` |
| Uncommon | `#1eff00` |
| Rare | `#0070dd` |
| Epic | `#a335ee` |
| Legendary | `#ff8000` |
| Artifact | `#e6cc80` |

---

## 🎨 Brand Assets

All brand assets are embedded as base64 data URIs in `forge-assets.js` and injected into the DOM on page load via `window.FA`.

### Using Assets in Your Pages

Every page loads `forge-assets.js` and uses `data-asset` attributes:

```html
<!-- In your HTML -->
<img data-asset="logo" src="" alt="ForgeWoW Database Logo">
<img data-asset="header_bg" src="" alt="">
<img data-asset="feat_search" src="" alt="Search">

<!-- forge-assets.js auto-fills all src="" attributes after DOMContentLoaded -->
```

### Available Asset Keys

| Key | Description |
|---|---|
| `logo` | Main logo — hammer + anvil + FORGE WoW DATABASE text (transparent bg) |
| `header_bg` | Header forge scene background image |
| `hero_bg` | Hero section background (forge anvil rune ring) |
| `page_bg` | Chainmail R-pattern page background tile |
| `button` | Forge button image (teal stone plaque with cyan gems) |
| `feat_search` | Advanced Search feature icon |
| `feat_maps` | Interactive Maps feature icon |
| `feat_items` | Item Database feature icon |
| `feat_lore` | Lore Guides feature icon |
| `icon_sword` | Weapon category sidebar icon |
| `icon_gear` | Armor category sidebar icon |
| `icon_ring` | Ring/accessory sidebar icon |
| `icon_spell` | Spell/pet sidebar icon |
| `icon_axe` | Axe weapon sidebar icon |
| `rune_tile` | Runic alphabet decorative tile |
| `infopab` | Mission statement text image |
| `silhouette` | Player character silhouette |

---

## 🎨 Design System

### Color Palette

```css
--gold:          #E6A11C   /* Molten Gold — primary accent */
--gold-bright:   #f5be45   /* Highlights and headings */
--gold-dim:      #9a6c0e   /* Borders and dimmed text */
--cyan:          #00C2FF   /* Runic Cyan — secondary accent */
--black:         #000000   /* Page background */
--blue-deep:     #030a14   /* Deep forge blue */
--blue-panel:    #08121f   /* Panel/card backgrounds */
```

### Typography

| Use | Font |
|---|---|
| Display / Logo | Cinzel Decorative (Google Fonts) |
| Headings / Nav | Cinzel (Google Fonts) |
| Body / Descriptions | Crimson Pro (Google Fonts) |

### Forge Button System

All buttons use the stone plaque image as a CSS background via `--btn-bg`:

```css
.forge-btn {
  position: relative;
  background: transparent;
  /* Image is applied via ::before pseudo-element */
}
.forge-btn::before {
  content: "";
  position: absolute;
  inset: 0;
  background-image: var(--btn-bg);
  background-size: 100% 100%;
}
.forge-btn span {
  position: relative;
  z-index: 1; /* Text floats above the image */
}
```

Size variants: `.forge-btn.sm` (38px) · `.forge-btn` (46px default) · `.forge-btn.lg` (54px)

---

## 🏠 Sister Site — WoWHousingDecor.com

**[www.WoWhousingdecor.com](https://www.wowhousingdecor.com)** is our dedicated companion site for World of Warcraft Player Housing.

If ForgeWoW covers every *item* in the game, WoWHousingDecor covers everything you need to *decorate your player home* — furniture, trophies, props, crafted decor, and room inspiration galleries.

| ForgeWoW Database | WoWHousingDecor.com |
|---|---|
| All WoW items & gear | Housing furniture & decor only |
| Weapons, armor, spells | Placement tips & room themes |
| Raid & dungeon data | Community home galleries |
| BiS & transmog tools | Seasonal & holiday decor |

---

## 📜 SEO Features

The site is built with SEO best practices throughout:

- Semantic HTML5 (`<article>`, `<section>`, `<nav>`, `<main>`, `<footer>`)
- Full `<meta>` tags: `description`, `keywords`, `robots`, `canonical`
- **Open Graph** tags for social sharing
- **Twitter Card** metadata
- **Schema.org JSON-LD** structured data:
  - `WebSite` with `SearchAction` (enables Google sitelinks search)
  - `FAQPage` on homepage (enables Google FAQ rich snippets)
- `aria-label` attributes on key sections for accessibility
- Keyword-rich copy covering all expansion names, item types, and WoW terminology

---

## 🛠 Tech Stack

| Layer | Technology |
|---|---|
| Markup | Vanilla HTML5 |
| Styles | Vanilla CSS3 (custom properties, grid, flexbox) |
| Scripts | Vanilla JavaScript (ES6+) |
| 3D Rendering | [Three.js r128](https://threejs.org/) via Cloudflare CDN |
| Fonts | Google Fonts (Cinzel Decorative, Cinzel, Crimson Pro) |
| Data | Blizzard Battle.net API (OAuth 2.0 client credentials) |
| Hosting | Any static web host (no server-side code required) |

**Zero dependencies to install.** No npm. No webpack. No React. Open in a browser and it works.

---

## 🔄 Data Update Workflow

ForgeWoW uses Blizzard's `client_credentials` OAuth flow — no user login required:

```
1. Browser → POST /oauth/token (Client ID + Secret)
            ← access_token (expires in 24h)

2. Browser → GET /data/wow/item/{id}?namespace=static-{region}&locale=en_US
            ← Full item data JSON

3. Browser → GET /data/wow/media/item/{id}
            ← Item icon URL

4. Token expires → Auto-refresh using stored Client ID/Secret
```

Everything happens client-side. No proxy server needed for development.

---

## 🤝 Contributing

Contributions are welcome! Here's how to help:

1. **Fork** the repository
2. **Create a branch** — `git checkout -b feature/your-feature-name`
3. **Make your changes**
4. **Test** by opening `index.html` in a browser
5. **Submit a Pull Request** with a clear description

### Good First Contributions

- Add more items to the demo data arrays in `items.html`
- Improve the BiS lists with accurate per-spec recommendations
- Add new lore articles to `lore.html`
- Improve mobile responsiveness
- Add missing expansion coverage to `maps.html`
- Write unit tests for the item filter/sort logic

---

## 🐛 Reporting Issues

Please include the following when reporting a bug:

- Browser and version
- Which page the issue occurs on
- Item ID (if data-related)
- Steps to reproduce
- Screenshot if applicable

---

## 📄 License

This project is licensed under the **MIT License** — see the [LICENSE](LICENSE) file for details.

---

## ⚠️ Disclaimer

World of Warcraft® and Blizzard Entertainment® are registered trademarks of Blizzard Entertainment, Inc. ForgeWoW Database is an independent, fan-made project and is **not affiliated with, endorsed by, or connected to Blizzard Entertainment** in any way.

Item data is accessed through the officially available [Blizzard Battle.net API](https://develop.battle.net/). All item names, descriptions, and game data are the intellectual property of Blizzard Entertainment, Inc.

---

## 🔗 Links

| Resource | URL |
|---|---|
| Live Site | [forgewowdatabase.com](https://forgewowdatabase.com) |
| Sister Site | [wowhousingdecor.com](https://www.wowhousingdecor.com) |
| Blizzard API Docs | [develop.battle.net](https://develop.battle.net/) |
| Three.js | [threejs.org](https://threejs.org/) |
| WoW Community | [worldofwarcraft.com](https://worldofwarcraft.com) |

---

<div align="center">

**⚒ Forged by the community, for the community ⚒**

[ForgeWoWdatabase.com](https://forgewowdatabase.com) · [WoWHousingDecor.com](https://www.wowhousingdecor.com)

</div>
