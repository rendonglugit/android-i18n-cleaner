# Android i18n Cleaner

<p align="center">
  <strong>A zero-dependency, 100% client-side web tool for batch cleaning and safely escaping Android internationalization (<code>strings.xml</code>) resources.</strong>
</p>

<p align="center">
  <a href="https://rendonglugit.github.io/android-i18n-cleaner/"><strong>🌐 Live Demo on GitHub Pages</strong></a>
</p>

<p align="center">
  English | <a href="README.zh-CN.md">简体中文</a>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Project-Android%20i18n%20Cleaner-blue?style=flat-square" alt="Project">
  <img src="https://img.shields.io/badge/Security-100%25%20Client--Side-brightgreen?style=flat-square" alt="Client-Side Only">
  <img src="https://img.shields.io/badge/Platform-Web%20(Cross--Platform)-blue?style=flat-square" alt="Platform">
  <img src="https://img.shields.io/badge/License-MIT-orange?style=flat-square" alt="License">
  <img src="https://img.shields.io/badge/GitHub%20Pages-Ready-success?style=flat-square" alt="GitHub Pages">
</p>

---

## 🚀 Live Demo

👉 **[Try the Tool Online (GitHub Pages)](https://rendonglugit.github.io/android-i18n-cleaner/)**

No installation, no CLI commands, and no administrative permissions required. Works out of the box in your web browser.

---

## 💡 Why This Web Tool?

In Android development, translating and managing localized XML strings often introduces formatting errors such as unescaped single quotes (`'`) or ampersands (`&`), and requires directory adjustments (e.g. `values-id` &rarr; `values-in`, dropping untranslated locales like `values-ur`).

Traditional shell scripts (`.sh` / `.command`) come with significant friction:
- ❌ **Permission Warnings**: macOS Gatekeeper blocks downloaded scripts ("unidentified developer"), requiring `chmod +x` or security overrides.
- ❌ **Environment Inconsistencies**: Strong dependencies on `perl` or `python3`; Windows teammates struggle without Git Bash or WSL.
- ❌ **Distribution Hassle**: Sharing scripts across teams requires manual file copying and environment debugging.

**This tool fixes all of that:**
- ✅ **Zero Permissions & Zero Friction**: Runs completely inside the browser sandbox without security prompts.
- ✅ **Cross-Platform**: Identical experience and performance on Windows, macOS, and Linux.
- ✅ **100% Client-Side & Private**: All file parsing, escaping, directory restructuring, and ZIP compression happen in your browser memory. **No data is uploaded to any server**.

---

## ⚡ Key Features

1. **Robust XML Escaping**:
   - `'` &rarr; `\'` (Idempotent: strings that are already escaped with `\'` will **not** be double-escaped).
   - `&` &rarr; `&amp;` (Strictly protects existing XML entities like `&amp;`, `&lt;`, `&gt;`, `&quot;`, `&apos;` without producing `&amp;amp;`).
2. **Directory Renaming**:
   - Preset with `values-id:values-in` (supporting legacy Indonesian locale mapping), fully customizable.
3. **Locale Trimming (Exclusion)**:
   - Easily drop unused language directories (e.g., `values-ur`) with one click.
4. **Three Flexible Modes**:
   - 📁 **Direct In-Place Directory Batch (Recommended)**: Powered by the Chromium *File System Access API* (`showDirectoryPicker`). Pick your Android `res` directory, back up automatically, and update XML files in-place.
   - 📦 **Universal ZIP / Folder Import & Export**: Compatible with all modern browsers (Chrome, Safari, Edge, Firefox). Drag & drop your folder or ZIP, and instantly download the processed result package.
   - ✍️ **Instant Text Snippet Tester**: Paste individual `<string>` blocks to inspect transformations and copy results immediately.
5. **Interactive Logging & Statistics**: Real-time inspection of modified files, skipped files, and transformed lines.

---

## 🛠️ Usage

### Option 1: Online (Recommended)
Visit the **[Live Demo](https://rendonglugit.github.io/android-i18n-cleaner/)** directly in any modern browser.

### Option 2: Run Locally
1. Clone or download this repository.
2. Double-click `index.html` to open it in your browser.

---

## 📦 Deployment to Your Own GitHub Pages

You can host this tool on your own GitHub Pages in under a minute:

1. Push this repository to GitHub:
   ```bash
   git init
   git add .
   git commit -m "feat: initial commit"
   git branch -M main
   git remote add origin https://github.com/rendonglugit/android-i18n-cleaner.git
   git push -u origin main
   ```
2. Navigate to your repository on GitHub:
   - Click **Settings** &rarr; **Pages** (in the left sidebar).
   - Under **Build and deployment**, set **Source** to `Deploy from a branch`.
   - Select branch `main` and folder `/ (root)`, then click **Save**.
3. Your web app will be live at:
   `https://rendonglugit.github.io/android-i18n-cleaner/`

---

## 📄 License

[MIT License](LICENSE) © 2026 rendonglugit
