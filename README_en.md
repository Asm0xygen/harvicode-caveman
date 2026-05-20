# 🦴 Caveman Mode for Harvi Code

> Radical token economy. Zero fluff. Maximum precision.

[![Harvi Code](https://img.shields.io/badge/Harvi-Code-blue)](https://harvi.code)
[![Token Savings](https://img.shields.io/badge/token_savings-~75%25-green)](#token-comparison)

---

## ⚡ What is it

**Caveman Mode** — specialized Harvi Code mode that reduces token usage by ~75% via telegraphic response style. Technical accuracy preserved. Fluff removed.

**Ideal for:**
- 🗂️ Large codebases
- 🔄 Long refactoring sessions
- 💰 Limited token budgets
- ⚡ Quick iterations and fixes

---

## 🎚️ Token Saving Levels

| Level | Style | Example |
|-------|-------|---------|
| `lite` | Moderate. No pleasantries, contractions OK | `Input validation before processing.` |
| `full` 🔹 | Aggressive. Drop articles/fillers, fragments OK | `Null pointer line 42. Check init.` |
| `ultra` | Extreme. ≤3 words/thought, symbols over words | `Line 15: x=null. Fix: add check.` |

🔹 `full` — default

---

## 🚀 Activation

```bash
/caveman          # full (default)
/caveman lite     # moderate
/caveman ultra    # extreme
```

---

## 📐 Principles

### Syntax
- ❌ No: articles, filler words, modals, pleasantries
- ✅ Yes: active voice, S+V+O, symbols (`->` `&` `=` `!=` `?` `!`)

### Format
- 1 thought = 1 bullet
- Code without wrappers if obvious
- Diff: changed lines only

### Icons instead of meta-text
| Action | Icon |
|--------|------|
| Read | 📖 |
| Write | 📝 |
| Create | 🛠️ |
| Delete | 🗑️ |
| OK | ✅ |
| Fail | ❌ |
| Warn | ⚠️ |

**Example:**
```
📖 config.toml
🛠️ utils.js: add null check
✅ Done.
```

---

## 💡 Examples

### Q → A
```
Q: What does this function do?
Standard: I'll help. This function validates user input...
Caveman: Input validation before processing.
```

### Error → Fix
```
Q: Why build fails?
Standard: Looks like missing dependency...
Caveman: ❌ package.json: missing `lodash`. Fix: npm install lodash.
```

### Code change
```
Input: Fix typo line 23
Standard: Sure! Here's the corrected code...
Caveman: 📝 index.js:23 → s/recieve/receive/ ✅
```

---

## ⚠️ When NOT to use

| Scenario | Reason |
|----------|--------|
| 👶 Teaching beginners | Need full explanations |
| 📚 User documentation | Requires complete, clear style |
| 🤝 Non-technical communication | Telegraphic style may confuse |
| 🏗️ Architecture discussions | Needs details and context |

---

## 📊 Token Comparison: "What is turbulence?"

| Metric | Standard Response | Caveman (full) |
|--------|------------------|----------------|
| Words | ~80 | ~20 |
| Tokens (est.) | ~110 | ~28 |
| Structure | Headers + lists + formula + examples | 2 sentences |
| Formula | Full: `Re = ρvL/μ` + explanation | Compressed: `Re > critical` |

**Savings calculation:**
```
(110 - 28) / 110 × 100% = ~75% ✅
```

**Standard:**
> Turbulence is a flow regime of fluid or gas where particle motion becomes chaotic, with vortex formation and velocity/pressure pulsations. Key features: chaotic particle motion, multi-scale vortices, intense layer mixing, pulsations. Determined by Reynolds number: Re = ρvL/μ. When exceeding critical value (usually 2000–4000 for pipes), laminar flow transitions to turbulent. Occurs in: atmospheric phenomena, rivers/pipes, aerodynamics, engines, circulatory system.

**Caveman:**
> Turbulence = chaotic fluid/gas motion with vortices & pulsations. Occurs when Re > critical (inertia > viscosity).

✅ Core meaning preserved: definition + mechanism + Re threshold  
❌ Removed: application examples, detailed features, visual structure


---

> 🦴 **Caveman Mode**: Less tokens. More code. Zero noise.


# Token Saving Rules Management


## Rules Structure

```
~/.harvi/rules/          # Global (all projects)
└── caveman-global.md    # Token saving everywhere

.project/.harvi/rules/   # Project-specific only
└── caveman-local.md     # Token saving in project
```

## Activation

### Globally (all projects)

**Windows:**

```cmd
# Create directory
if not exist "%USERPROFILE%\.harvi\rules" mkdir "%USERPROFILE%\.harvi\rules"

# Create file
echo. > "%USERPROFILE%\.harvi\rules\caveman-global.md"

# Or copy template
copy caveman-global.md "%USERPROFILE%\.harvi\rules\"
```

**Linux/Mac:**

```bash
# Create directory
mkdir -p ~/.harvi/rules

# Create file
touch ~/.harvi/rules/caveman-global.md

# Or copy template
cp caveman-global.md ~/.harvi/rules/
```

### For Project

**Windows:**

```cmd
mkdir .harvi\rules
echo. > .harvi\rules\caveman-local.md
```

**Linux/Mac:**

```bash
mkdir -p .harvi/rules
touch .harvi/rules/caveman-local.md
```

## Deactivation

### Temporarily (rename)

**Windows:**

```cmd
# Global
ren "%USERPROFILE%\.harvi\rules\caveman-global.md" caveman-global.md.off

# Project
ren .harvi\rules\caveman-local.md caveman-local.md.off
```

**Linux/Mac:**

```bash
# Global
mv ~/.harvi/rules/caveman-global.md ~/.harvi/rules/caveman-global.md.off

# Project
mv .harvi/rules/caveman-local.md .harvi/rules/caveman-local.md.off
```

### Permanently (delete)

**Windows:**

```cmd
# Global
del "%USERPROFILE%\.harvi\rules\caveman-global.md"

# Project
del .harvi\rules\caveman-local.md
```

**Linux/Mac:**

```bash
# Global
rm ~/.harvi/rules/caveman-global.md

# Project
rm .harvi/rules/caveman-local.md
```

### Disable All Rules

**Windows:**

```cmd
ren "%USERPROFILE%\.harvi\rules" rules.off
```

**Linux/Mac:**

```bash
mv ~/.harvi/rules ~/.harvi/rules.off
```

### Restore

**Windows:**

```cmd
ren "%USERPROFILE%\.harvi\rules.off" rules
```

**Linux/Mac:**

```bash
mv ~/.harvi/rules.off ~/.harvi/rules
```

## Priority

1. Mode rules — highest priority
2. Project rules — medium priority
3. Global rules — lowest priority

## Verification

Rules load at session start. Visible in system prompt:
```
# Rules from ~/.harvi/rules/*.md
# Rules from .harvi/rules-<mode>/*.md
```

## Quick Commands

**Windows:**

```cmd
# Enable saving
copy templates\caveman-global.md "%USERPROFILE%\.harvi\rules\"

# Disable saving
ren "%USERPROFILE%\.harvi\rules\caveman-global.md" caveman-global.md.off

# Check existence
dir "%USERPROFILE%\.harvi\rules\*.md"
```

**Linux/Mac:**

```bash
# Enable saving
cp templates/caveman-global.md ~/.harvi/rules/

# Disable saving
mv ~/.harvi/rules/caveman-global.md ~/.harvi/rules/caveman-global.md.off

# Check existence
ls ~/.harvi/rules/*.md
```

---

## 📄 License

MIT — use, modify, share.