# Alphatasker

**RPA bot that creates work orders in bulk, with scheduling rules per order type.**
Windows desktop app used daily by an HVAC operations team · current version **v0.3.8**

`Python` `Selenium 4` `pywebview / WebView2` `PyInstaller` `Inno Setup` `GitHub Releases API`

---

## The problem

Opening work orders in a web maintenance system meant filling the same long form over and over, and spacing start times by hand. Alphatasker turns that into filling a grid and clicking **one button**.

## What it does

- **Spreadsheet-style grid:** sector autocomplete over **500+ sectors** (accent-insensitive), plus pickers for occurrence, cause and type. A new row appears as you finish the previous one.
- **Scheduling rules:** the first order of each day starts at 08:00, and the next start time is spaced automatically by order type.
- **Live monitor** with pause, restart and stop while the bot creates every order in the browser.

## How it's built

- **Worker process plus orchestrator:** the bot runs apart from the UI, which talks to it through a JS ↔ Python bridge (pywebview / WebView2). The WebView2 runtime ships inside the installer.
- **Custom browser-driver resolver:** it detects the installed Edge version, downloads the matching driver and caches it, with a fallback to webdriver-manager and Chrome.
- **Credentials encrypted locally:** the operator types them once.
- **Self-updating** through the GitHub Releases API, with a scripted pipeline that runs the version bump, PyInstaller build, Inno Setup installer and release.

> Source code is private. This repository only hosts the installer and auto-update releases.

---

## 🇧🇷 Download

**[Baixar AlphataskerSetup.exe](https://github.com/Sharkvlr/alphatasker/releases/latest/download/AlphataskerSetup.exe)**

Depois de baixar, execute o instalador e siga as instruções. O app se atualiza sozinho.

---

© 2026 Gabriel Adley. All rights reserved.
