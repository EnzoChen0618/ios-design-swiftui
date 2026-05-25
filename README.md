# ios-design-swiftui

> 🍎 A Claude AI Skill that generates production-quality SwiftUI — 17 app domains, 4 visual styles, Apple HIG enforced by default.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/Platform-iOS%2017%2B-lightgrey.svg)](https://developer.apple.com/swiftui/)
[![Claude Skill](https://img.shields.io/badge/Claude-Skill-orange.svg)](https://claude.ai)

---

## What is this?

`ios-design-swiftui` is a Claude AI Skill that turns Claude into a senior Apple ecosystem experience architect. It enforces Apple's Human Interface Guidelines, auto-configures per-domain themes, and outputs SwiftUI code that looks and feels like it shipped with iOS — before writing a single line of code.

Most AI design skills are built for the web (React, shadcn, Tailwind). This one is built exclusively for **iOS native**, with deep knowledge of SwiftUI idioms, SF Symbols, Dynamic Type, VoiceOver, and Apple's visual language.

---

## Features

### 🎨 Aesthetic & Architecture Prelude
Before any code is generated, Claude declares:
- Visual tone, depth model, motion philosophy
- View hierarchy blueprint (full component tree)
- HIG compliance checklist

### 🧠 17-Domain Smart Theme Engine
Describe your app — the skill auto-detects the domain and configures the complete visual stack:

| Domain | Primary Color | Default Style |
|---|---|---|
| 金融理财 Finance | `#1A5CFF` Royal Blue | Glassmorphic |
| 健康医疗 Health | `#FF3B30` Vitality Red | Glassmorphic |
| 社交娱乐 Social | `#FF375F` Vibrant Pink | Vibrant |
| 效率工具 Productivity | `#0071E3` Apple Blue | Minimal |
| 电商购物 Commerce | `#FF6B00` Orange | Vibrant |
| 教育学习 Education | `#5856D6` Indigo | Vibrant |
| 旅行出行 Travel | `#32ADE6` Sky Blue | Glassmorphic |
| 媒体内容 Media | `#1C1C1E` Deep Black | Dark First |
| 餐饮美食 Food | `#FF6D00` Warm Orange | Vibrant |
| 音乐播客 Music | `#BF5AF2` Purple | Dark First |
| 房产租房 Real Estate | `#1565C0` Deep Blue | Minimal |
| 求职招聘 Jobs | `#283593` Navy | Minimal |
| 游戏中心 Gaming | `#E94560` Neon Red | Dark First |
| 天气 Weather | `#0277BD` Sky Blue | Glassmorphic |
| 加密/Web3 Crypto | `#FF8F00` Gold | Dark First |
| 宠物生活 Pets | `#AD1457` Warm Pink | Vibrant |
| 系统工具 Utility | `#8E8E93` Gray | Minimal |

### 🎭 4 Visual Style Variants

| Style | Character | Best For |
|---|---|---|
| **Minimal** | Pure signal, zero decoration, weight contrast drives hierarchy | Productivity, Jobs, Utility |
| **Dark First** | Depth, drama, neon accents, colored glow shadows | Music, Gaming, Crypto |
| **Glassmorphic** | `.ultraThinMaterial`, gradient heroes, layered depth | Finance, Health, Weather |
| **Vibrant** | Bold color, SF Rounded, bouncy springs, pill buttons | Social, Food, Pets |

### 📐 Typography & Component Standards
- **Dynamic Type only** — zero hardcoded font sizes, ever
- **Native components first** — `NavigationStack`, `List`, `.sheet`, `.searchable`
- **8pt/16pt spacing grid** — `Spacing.xs/sm/md/lg/xl` tokens

### ♿️ Accessibility & Motion
- Mandatory VoiceOver: `accessibilityLabel`, `accessibilityHint`, `.combine`, `.isHeader`
- `@Environment(\.accessibilityReduceMotion)` guard on every animation
- Spring values tuned per style variant

---

## Slash Commands

| Command | Description |
|---|---|
| `/audit` | Score UI against Nielsen's 10 Heuristics + Apple HIG. Returns a scored table with 🔴/🟡/🟢 findings and corrected code snippets. |
| `/theme [domain]` | Swap domain theme (e.g. `/theme music`). Updates all color/material/symbol tokens with a before/after diff. |
| `/style [variant]` | Switch visual style without changing brand colors (e.g. `/style dark`). Updates backgrounds, cards, shadows, springs. |
| `/template [domain] [screen]` | Generate a complete polished screen (e.g. `/template music player`, `/template weather today`). |
| `/polish` | Refactor: extract reusable Views, normalize modifier order, lift state to ViewModel, replace magic numbers with tokens. |
| `/darkmode` | Convert any light-mode view to a Dark First variant. |

---

## Quick Start

### 1. Install the skill
Download `ios-design-swiftui.skill` and open it in **Claude for Desktop** (Cowork mode).

### 2. Describe your screen
```
帮我写一个音乐 App 的播放器页面
```
Claude auto-detects: Music → Dark First style → `#BF5AF2` purple theme  
Then outputs: Aesthetic Intent Declaration → View Hierarchy Blueprint → full SwiftUI `NowPlayingView`

### 3. Use slash commands
```
/template weather today
/style glass
/audit [paste your SwiftUI code]
/theme crypto
```

---

## Example Output

**Input:** `帮我写一个金融理财 App 的资产总览页面`

**Output includes:**
- 🎨 Aesthetic Intent: "临危不乱的专业感 + 数字带来的掌控感"
- 🏗 View Hierarchy: `NavigationStack → ScrollView → TotalAssetsHeroCard + QuickActionsRow + AssetCategorySection + RecentTransactionSection`
- 🎨 Finance theme tokens (`#1A5CFF`, `.ultraThinMaterial`, `.hierarchical`)
- Complete SwiftUI with Dark Mode, VoiceOver, spring animations, 8pt spacing grid

---

## Requirements

- **Claude for Desktop** with Cowork mode (or any Claude environment supporting Skills)
- Generated SwiftUI targets **iOS 17+**
- Xcode 15+ recommended for `@Observable` macro support

---

## Repository Structure

```
ios-design-swiftui/
├── README.md
├── SKILL.md                  ← Full skill prompt (17 domains, 4 styles, 6 commands)
└── ios-design-swiftui.skill  ← Installable skill package
```

---

## Philosophy

> *"Every output should be something Jony Ive would not wince at and Phil Schiller would feel comfortable demoing on stage."*

The gap between "AI-generated UI" and "Apple-quality UI" is almost entirely about discipline — enforcing the right constraints before writing code. `ios-design-swiftui` is that discipline, systematized.

---

## Roadmap

- [ ] Per-domain template library (3–5 screens per domain)
- [ ] SwiftUI component snippet library
- [ ] watchOS & iPadOS layout variants
- [ ] Figma → SwiftUI translation mode

---

## License

MIT — use freely, modify freely, ship great iOS apps.
