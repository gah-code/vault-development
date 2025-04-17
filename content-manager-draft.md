Walk through setting up a **daily & weekly Content Manager workflow** using Templater, with auto-generated notes, phase tracking, and internal linking for your 60-day onboarding plan for new role.

---

# 🧠 Obsidian 60-Day Content Manager Workflow

Welcome! This Obsidian vault is configured to support your 60-day onboarding and work cycle as a **Content Manager at Hogarth** using **Adobe Experience Manager (AEM)**. It includes:

✅ Automatic daily & weekly logs  
✅ Smart phase tracking (Onboarding → Ramp-Up → Ownership)  
✅ Auto-links between logs & summaries  
✅ Templater snippets for repeatable workflows  

---

## 📁 Folder Structure

```bash
/Hogarth-Content-Manager/
├── 📆 Daily Logs/
│   └── 2025-04-29.md (auto-generated)
├── 📅 Weekly Reviews/
│   └── Week 2025-W18 Summary – Content Manager Log.md
├── 📋 60-Day Plan.md
├── 📁 Templates/
│   ├── daily-log.md
│   └── weekly-summary.md
├── 📁 Scripts/
│   └── daily-log-startup.js (optional automation)
```

---

## 🔌 Plugin Requirements

### ✅ 1. [Templater Plugin](https://github.com/SilentVoid13/Templater)

- Install from **Community Plugins**
- Enable and set your `Template Folder Location` to `Templates`

---

## 🗓️ Daily Log Template Setup

📄 `Templates/daily-log.md`

```js
<%*
const today = tp.date.now("YYYY-MM-DD")
const week = tp.date.now("WW")
const year = tp.date.now("gggg")
const weeklyLink = `[[Weekly Reviews/Week ${year}-W${week} Summary – Content Manager Log]]`

const start = moment("2025-04-29", "YYYY-MM-DD")
const dayDiff = moment().diff(start, 'days') + 1

let phase = ""
if (dayDiff <= 15) phase = "Phase 1 – Onboarding & Orientation"
else if (dayDiff <= 35) phase = "Phase 2 – Ramp-Up & Contribution"
else if (dayDiff <= 60) phase = "Phase 3 – Project Ownership & Process Optimization"
else phase = "🚨 Past 60 Days – Add Reflection!"
%>

# 📆 <%= today %> – Daily Log

> [!info] Context  
> Week <%= week %> | Day <%= dayDiff %> of 60 | Phase: [[<%= phase %>]]  
> Connected Weekly Summary: <%= weeklyLink %>

## ✅ Tasks Completed
- [ ] 
- [ ] 

## ⌛ Time Spent
- Content Management:
- Meetings:
- QA/Testing:
- Learning:

## 🔄 In Progress
- [ ] 
- [ ] 

## 🧠 Notes & Observations
- 
- 

## 📌 Tags
`#daily-log` `#week-<%= week %>` `#phase-<%= phase.toLowerCase().replace(/\s+/g, "-") %>` `#content-manager`
```

---

## 📅 Weekly Summary Template Setup

📄 `Templates/weekly-summary.md`

```js
<%*
const week = tp.date.now("WW")
const year = tp.date.now("gggg")
const start = moment("2025-04-29", "YYYY-MM-DD")
const dayDiff = moment().diff(start, 'days') + 1

const phase = (dayDiff <= 15) ? "Phase 1 – Onboarding & Orientation" :
              (dayDiff <= 35) ? "Phase 2 – Ramp-Up & Contribution" :
              (dayDiff <= 60) ? "Phase 3 – Project Ownership & Process Optimization" :
              "🚨 Past 60 Days – Reflect!"
%>

# 🗂️ Week <%= year %>-W<%= week %> Summary – Content Manager Log

> [!info] Phase: [[<%= phase %>]] | Approx. Day: <%= dayDiff %>

## 🎯 Weekly Goals
- [ ] 
- [ ] 
- [ ] 

## ✅ Highlights
- 

## ⚠️ Challenges / Risks
- 

## 🔁 Feedback / Ideas
- 

## 🧠 Reflection
- 

## 📌 Tags
`#weekly-review` `#week-<%= week %>` `#aem` `#content-manager` `#<%= phase.toLowerCase().replace(/\s+/g, "-") %>`
```

---

## 🧪 Optional: Auto-Create Daily Note on Startup

📄 `Scripts/daily-log-startup.js`  
> Place this in: `.obsidian/plugins/templater/scripts/`

```js
module.exports = async (tp) => {
  const today = tp.date.now("YYYY-MM-DD");
  const path = `Daily Logs/${today}.md`;
  if (!await app.vault.adapter.exists(path)) {
    await tp.file.create_new(tp.file.find_tfile("daily-log"), path, false);
  }
};
```

Then go to:  
`Settings → Templater → Trigger Templater user script on Obsidian startup → daily-log-startup.js`

---

## ⚡ How to Use

### 🧭 Option 1: Use from Command Palette

- Press `Cmd/Ctrl + P` → `Templater: Create new note from template`
- Choose `daily-log.md` or `weekly-summary.md`

### ⌨️ Option 2: Set Hotkeys

Go to `Settings → Hotkeys` and assign shortcuts to:

- `Templater: Create new note from template` → daily-log
- `Templater: Create new note from template` → weekly-summary

---

## 🔗 Bonus Features (Optional Ideas)

| Feature | Description |
|--------|-------------|
| `Dataview` integration | Roll up completed tasks by week/phase |
| `Canvas` dashboard | Drag and drop logs, phases, summaries into a workspace |
| `Periodic Reviews` | Add monthly or retrospective templates |
| `Daily Highlight` | Track wins or blockers across 60 days for performance review |

---

## 🧩 Recommended Tags for Filtering

Use these for quick searches and dashboards:

- `#daily-log`
- `#weekly-review`
- `#content-manager`
- `#aem`
- `#phase-1-onboarding`
- `#phase-2-ramp-up`
- `#phase-3-ownership`

---

Next Steps

- A `Dataview` dashboard for your tasks
- Monthly auto-summary script
- Integration with your `60-Day Plan.md`

Onboarding and documentation workflow! 🚀
