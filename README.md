# 🌸 Amore — Daily Girl Companion

A beautiful, soft, all-in-one daily wellness website for girls. No backend needed — fully runs in the browser with `localStorage`.

## Features

| Widget | What it does |
|---|---|
| **Daily Affirmation** | Rotating positive affirmations — tap for a new one |
| **Mood Tracker** | Log your mood + optional note with timestamps |
| **Hydration Tracker** | 8-glass water tracker, resets each day |
| **Habit Tracker** | Check off daily habits with streak counters + add your own |
| **Journal** | Daily writing prompt + free text journal, auto-saved locally |
| **AM Skincare Routine** | Step-by-step morning skincare checklist |

## How to run

Just open `index.html` in any browser. No server, no install needed.

## Tech stack

- Pure HTML + CSS + Vanilla JS
- `localStorage` for persistence
- Google Fonts: Playfair Display + DM Sans
- Zero dependencies

## Customization

- **Colors** → edit CSS variables in `:root { ... }`
- **Affirmations** → edit the `affirmations` array in the script
- **Journal prompts** → edit `journalPrompts` array
- **Default habits** → edit `defaultHabits` array
- **Skincare steps** → edit `skinSteps` array

---
Made with love 🌸

## Architecture

```
User (browser)
      │
      ▼
  index.html  ──────────────────────────────┐
      │                                     │
  ┌───┴─────────────┐              Google Fonts CDN
  │                 │              (Playfair Display
  ▼                 ▼               + DM Sans + Caveat)
HTML structure    CSS styles
(6 widget cards)  (vars, layout)
                       │
                  JavaScript (logic + state)
                       │
       ┌───────────────┼──────────────────┐
       ▼               ▼                  ▼
    Mood           Affirmation          Water
    tracker          (quotes)          tracker
       │               │                  │
    Habits           Journal           Skincare
    (streaks)       (notebook)         (AM routine)
       │               │                  │
       └───────────────┴──────────────────┘
                        │
                        ▼
              localStorage (browser)
        mood · water · habits · journal · skin
                        │
                        ▼
           Persists across sessions
        no server · no database · 100% offline
```

### Key design decisions

**No backend** — everything runs client-side. `localStorage` stores all user data keyed by date and feature, e.g. `bloom_journal_Fri Apr 04 2025`, `bloom_water`, `bloom_habits`.

**Single file** — the entire app is one `index.html`. No build step, no npm, no config. Open and it works.

**Zero runtime dependencies** — only Google Fonts (CDN, optional). All logic is vanilla JS.

**Graceful defaults** — if `localStorage` is empty, the app ships with 5 default habits, 9 affirmations, 7 journal prompts, and a 5-step skincare routine so it feels alive from the first load.

