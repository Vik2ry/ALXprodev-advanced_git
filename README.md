# ALXprodev-advanced_git

This repository demonstrates an advanced Git workflow using Git Flow and custom Git hooks.

## 📌 Features

- Git Flow structure: `main`, `develop`, `feature/*`, `release/*`
- Feature branches for login and signup pages
- Merged into `develop` and released under `release/1.0.0`
- Tagged release: `v1.0.0`

## 🔧 Git Hooks Implemented

### 1. `pre-commit` Hook
Ensures that every top-level directory contains a `README.md` file before allowing a commit.

- Location: `.git/hooks/pre-commit`
- Usage: Automatically runs on `git commit`
- Purpose: Enforces documentation discipline across directories

### 2. `post-merge` Hook
Logs every successful merge into the `main` branch into a `merge_log.txt` file.

- Location: `.git/hooks/post-merge`
- Usage: Automatically runs on `git merge`
- Log file: `merge_log.txt`

## ⚙️ Setup Instructions

To activate hooks:

```bash
chmod +x .git/hooks/pre-commit
chmod +x .git/hooks/post-merge