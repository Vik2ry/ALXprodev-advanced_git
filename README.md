# 🚀 ALXprodev Advanced Git Workflow

![Git](https://img.shields.io/badge/git-flow-blue?logo=git)
![Hooks](https://img.shields.io/badge/git--hooks-enabled-brightgreen)
![Status](https://img.shields.io/badge/version-v1.0.0-blueviolet)

This repository demonstrates a professional Git setup using **Git Flow** and custom **Git hooks** to ensure clean collaboration and consistent documentation across all development stages.

---

## 📌 Key Features

- Adopts the **Git Flow branching model**, including:
  - `main` – for production-ready code
  - `develop` – integration branch for completed features
  - `feature/*` – individual feature branches (e.g. `feature/login`)
  - `release/*` – pre-production releases (e.g. `release/1.0.0`)
- Feature branches include:
  - **Login page**
  - **Signup page**
- Merged into `develop`, then released via `release/1.0.0`
- Final version tagged as **`v1.0.0`**

---

## 🔁 Git Flow Diagram

\`\`\`plaintext
main
 │
 ├──◄───── release/1.0.0
 │          ▲
 │          │
 │     ─────┘
 │    develop
 │     ▲   ▲
 │     │   │
 │ ── feature/login
 │ ── feature/signup
\`\`\`

---

## 🔧 Custom Git Hooks

### 🧷 1. \`pre-commit\` Hook

✔ Validates that each **top-level directory contains a \`README.md\`** file.  
Prevents commits that don't follow the documentation policy.

- 📍 Location: \`.git/hooks/pre-commit\`
- ⚙️ Triggered by: \`git commit\`
- 🎯 Purpose: Enforces documentation discipline

---

### 🧷 2. \`post-merge\` Hook

✔ After merging into \`main\`, logs the merge event with a timestamp in \`merge_log.txt\`.

- 📍 Location: \`.git/hooks/post-merge\`
- ⚙️ Triggered by: \`git merge\`
- 🗃️ Output file: \`merge_log.txt\`

---

## 📘 Example \`merge_log.txt\` Output

\`\`\`txt
[2025-06-20 10:32:45] Merged release/1.0.0 into main by user: segunbanji
[2025-06-19 09:05:21] Merged hotfix/typo-fix into main by user: segunbanji
\`\`\`

---

## ⚙️ Hook Activation

Make both hook scripts executable:

```bash
chmod +x .git/hooks/pre-commit
chmod +x .git/hooks/post-merge