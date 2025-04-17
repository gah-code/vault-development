# 🧠 Obsidian 60‑Day Content‑Manager Workflow  

*A turnkey vault for ramping up as a Content Manager at Hogarth (AEM)*

---

## Table of Contents

1. [Overview](#overview)  
2. [Folder Structure](#folder-structure)  
3. [Quick Start](#quick-start)  
4. [Automated Setup Script](#automated-setup-script)  
5. [Plugin Installation](#plugin-installation)  

## Overview

This vault scaffolds everything you need for a **60‑day onboarding cycle**:

| Feature | Details |
|---------|---------|
| **Daily & Weekly logs** | One‑click generation via **Templater** |
| **Phase tracking** | Auto‑detects Day 1‑60 → assigns Phase 1/2/3 tags |
| **Auto‑linking** | Daily ↔ Weekly notes inter‑connected |
| **Startup script** | Creates today’s daily note when Obsidian opens |
| **Dataview snippets** | Quick dashboards for progress reviews |

---

## Folder Structure

```text
Hogarth-Content-Manager/
├── 00-Resources/
│   └── 60-Day Plan.md
├── Daily Logs/                # Daily notes
├── Weekly Reviews/            # Weekly notes
├── Templates/                 # Templater snippets
│   ├── daily-log.md
│   └── weekly-summary.md
├── Scripts/
│   └── daily-log-startup.js   # Auto‑create today’s note
├── README.md                  # This file
└── setup_obsidian_vault.sh    # One‑shot setup script
```

---

## Quick Start

1. **Clone / download** this repo **or** run the setup script (below) in an empty directory.  
2. **Open the folder** as a vault in Obsidian.  
3. **Install plugins**: Templater & Dataview (Calendar / Periodic Notes optional).  
4. **Templater settings** → template folder = `Templates/`.  
5. *(Optional)* Enable *run user script on startup* → `Scripts/daily-log-startup.js`.

You’re ready—press `<kbd>Cmd/Ctrl + P</kbd> → Templater → Create new note from template` and choose **daily‑log.md**.

---

## Automated Setup Script

Run this if you’re starting from scratch.

## WORKING ON IT
