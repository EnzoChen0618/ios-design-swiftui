# ios-design-swiftui

> 🍎 A system prompt that turns any AI into a senior Apple ecosystem architect — SwiftUI code that looks and feels like it shipped with iOS.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
[![Platform](https://img.shields.io/badge/iOS-17%2B-lightgrey.svg)](https://developer.apple.com/swiftui/)
[![SwiftUI](https://img.shields.io/badge/SwiftUI-ready-orange.svg)](https://developer.apple.com/xcode/swiftui/)

---

## What is this?

`ios-design-swiftui` is a structured system prompt for AI-assisted iOS development. Paste it into any AI assistant and it instantly enforces Apple Human Interface Guidelines, auto-configures per-domain themes, and generates production-quality SwiftUI — before writing a single line of code.

Most AI design prompts are built for the web (React, shadcn, Tailwind). This one is built exclusively for **iOS native**, with deep knowledge of SwiftUI idioms, SF Symbols, Dynamic Type, VoiceOver, and Apple's visual language.

**Works with:** ChatGPT · Cursor · GitHub Copilot · Claude · Gemini · Any LLM with a system prompt

---

## Quick Start

### ChatGPT / Gemini
1. Open a new conversation
2. Copy the contents of `SKILL.md`
3. Paste as your first message (or as a Custom Instruction in ChatGPT settings)
4. Start describing your iOS screen

### Cursor / VS Code Copilot
1. Copy `SKILL.md` contents
2. Add to `.cursor/rules` or your Copilot system prompt file
3. The prompt activates for all SwiftUI files in your project

### Claude (Desktop)
1. Install `ios-design-swiftui.skill` directly — double-click or drag into the Skills panel
2. Works automatically whenever you describe an iOS UI task

### API / Custom Integration
```python
with open("SKILL.md", "r") as f:
    system_prompt = f.read()

response = client.chat.completions.create(
    model="gpt-4o",  # or any model
    messages=[
        {"role": "system", "content": system_prompt},
        {"role": "user", "content": "帮我写一个音乐 App 的播放器页面"}
    ]
)
```

---

## Features

### 🎨 Aesthetic & Architecture Prelude
Before any code is generated, the AI declares:
- Visual tone, depth model, motion philosophy
- Full View Hierarchy Blueprint (component tree)
- Apple HIG compliance checklist

### 🧠 17-Domain Smart Theme Engine
Describe your app — the domain is auto-detected and the full visual stack is configured:

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
| **Minimal** | Pure signal, zero decoration, weight contrast | Productivity, Jobs, Utility |
| **Dark First** | Depth, drama, neon accents, glow shadows | Music, Gaming, Crypto |
| **Glassmorphic** | `.ultraThinMaterial`, gradient heroes, layered depth | Finance, Health, Weather |
| **Vibrant** | Bold color, SF Rounded, bouncy springs, pill buttons | Social, Food, Pets |

### 📐 Typography & Component Standards
- **Dynamic Type only** — zero hardcoded font sizes, ever
- **Native components first** — `NavigationStack`, `List`, `.sheet`, `.searchable`
- **8pt/16pt spacing grid** — `Spacing.xs/sm/md/lg/xl` tokens throughout

### ♿️ Accessibility & Motion
- Mandatory VoiceOver: `accessibilityLabel`, `accessibilityHint`, `.combine`, `.isHeader`
- `@Environment(\.accessibilityReduceMotion)` guard on every animation
- Spring values tuned per style variant (calm finance → bouncy social)

---

## Slash Commands

These commands work in any conversational AI — just type them:

| Command | Description |
|---|---|
| `/audit` | Score UI against Nielsen's 10 Heuristics + Apple HIG. Returns a scored table with 🔴/🟡/🟢 findings and corrected code. |
| `/theme [domain]` | Swap domain theme (e.g. `/theme music`). Updates all color/material/symbol tokens with a diff. |
| `/style [variant]` | Switch visual style without changing brand colors (e.g. `/style dark`). Updates backgrounds, cards, shadows, springs. |
| `/template [domain] [screen]` | Generate a full screen (e.g. `/template music player`, `/template weather today`). |
| `/polish` | Refactor: extract reusable Views, normalize modifier order, lift state to ViewModel, replace magic numbers. |
| `/darkmode` | Convert any light-mode view to a Dark First variant. |

---

## Example

**Prompt:** `帮我写一个金融理财 App 的资产总览页面`

**The AI will output:**
1. 🎨 **Aesthetic Intent** — "临危不乱的专业感 + 数字带来的掌控感"
2. 🏗 **View Hierarchy** — `NavigationStack → ScrollView → HeroCard + QuickActions + CategoryList + Transactions`
3. 🎨 **Theme Tokens** — `#1A5CFF`, `.ultraThinMaterial`, `.hierarchical` SF Symbols
4. **Complete SwiftUI** — Dark Mode adaptive, VoiceOver, spring animations, 8pt spacing grid

---

## Repository Structure

```
ios-design-swiftui/
├── README.md                   ← This file
├── SKILL.md                    ← The full system prompt (copy this into any AI)
└── ios-design-swiftui.skill    ← One-click install for Claude Desktop
```

---

## Requirements

- Generated SwiftUI targets **iOS 17+**
- Xcode 15+ recommended (`@Observable` macro support)
- Any AI assistant capable of receiving a system prompt

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
