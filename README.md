<div align="center">

# HeLLM — Next-Gen AI Exam & Form Solver Suite

**High-Performance Native C++ DirectX 11 Core • Stealth Chromium Extension • Serverless Cloud AI Backend**

[![C++20](https://img.shields.io/badge/Language-C%2B%2B20-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)](https://isocpp.org/)
[![DirectX 11](https://img.shields.io/badge/Graphics-DirectX%2011-0078D7?style=for-the-badge&logo=windows&logoColor=white)](https://learn.microsoft.com/en-us/windows/win32/direct3d11/direct3d-11-graphics)
[![Dear ImGui](https://img.shields.io/badge/GUI-Dear%20ImGui-grey?style=for-the-badge)](https://github.com/ocornut/imgui)
[![Manifest V3](https://img.shields.io/badge/Extension-Manifest%20V3-4285F4?style=for-the-badge&logo=google-chrome&logoColor=white)](https://developer.chrome.com/docs/extensions/mv3/)
[![Vercel Serverless](https://img.shields.io/badge/Backend-Vercel%20Node.js-000000?style=for-the-badge&logo=vercel&logoColor=white)](https://vercel.com/)
[![KeyAuth](https://img.shields.io/badge/Security-KeyAuth%20HWID-5865F2?style=for-the-badge)](https://keyauth.cc/)

<p align="center">
  <b>HeLLM</b> is an enterprise-grade, ultra-low latency AI-powered exam and quiz assistant designed for maximum accuracy, stealth, and cross-platform flexibility.
</p>

</div>

---

## Table of Contents
- [Overview & Architecture](#-overview--architecture)
- [Key Features](#-key-features)
  - [1. Pure Native C++ Desktop Application](#1-pure-native-c-desktop-application)
  - [2. Stealth Chromium Browser Extension](#2-stealth-chromium-browser-extension)
  - [3. Cloud Serverless AI Pipeline](#3-cloud-serverless-ai-pipeline)
  - [4. Global Analytics & AI Leaderboard](#4-global-analytics--ai-leaderboard)
- [Supported Platforms](#-supported-platforms)
- [Security & Anti-Abuse](#-security--anti-abuse)
- [Keyboard Shortcuts & Hotkeys](#-keyboard-shortcuts--hotkeys)
- [Getting Started & Installation](#-getting-started--installation)
  - [A. Running Desktop App](#a-running-desktop-app)
  - [B. Installing Browser Extension](#b-installing-browser-extension)
  - [C. Deploying Vercel Backend](#c-deploying-vercel-backend)
- [Disclaimer](#-disclaimer)

---

## Overview & Architecture

HeLLM employs a **3-tier decoupled architecture** designed to protect API credentials, ensure sub-150ms response times, and isolate client applications:

```
┌────────────────────────────────────────────────────────┐
│             Chromium Browser (Brave / Chrome)          │
│   • Stealth Focus Faker (Anti-Tab Switch Blocker)      │
│   • In-Page Floating HUD (Draggable, Opacity Slider)   │
│   • Vision OCR Area Cropper & GForm Auto-Filler        │
└─────────────────────────▲──────────────────────────────┘
                          │ Local IPC Socket (HTTP / JSON)
                          │ Port: 127.0.0.1:8765
┌─────────────────────────▼──────────────────────────────┐
│             HeLLM.exe Desktop Core (C++ / DX11)        │
│   • Dear ImGui Modern Monochrome Interface             │
│   • KeyAuth Cryptographic HWID License Gate            │
│   • Global Analytics & AI Leaderboard Engine           │
│   • Ephemeral Dynamic Session Token Generator          │
└─────────────────────────▲──────────────────────────────┘
                          │ HTTPS / TLS (Encrypted)
                          │ Zero Upstream Keys on Client
┌─────────────────────────▼──────────────────────────────┐
│             Vercel Serverless Cloud Backend            │
│   • Sliding-Window Rate Limiter & Cooldown Guard       │
│   • Dynamic Model Evaluated Probabilistic Confidence   │
│   • Upstream AI (Gemini 3.7, GLM-4.7, DeepSeek R1)     │
└────────────────────────────────────────────────────────┘
```

---

## Key Features

### 1. Pure Native C++ Desktop Application
* **Zero-Runtime Overhead**: Built in pure C++20 with DirectX 11 and Dear ImGui for instantaneous launch times and minimal RAM usage (< 30 MB).
* **Live Question Review Queue**: Review, edit, and approve extracted questions before filling them into forms.
* **Instant GForm Pre-filled URL Generator**: 1-click generation of Google Forms links with all answers pre-selected via `usp=pp_url`.
* **Zero-Access License Protection**: All local IPC socket endpoints reject unactivated requests with `403 Forbidden` until a valid KeyAuth license is verified.

### 2. Stealth Chromium Browser Extension
* **Stealth Focus Faker (Anti-Tab-Switching)**: Overrides `document.hidden`, `visibilitychange`, and `window.blur` events so test platforms never detect when you switch windows or lose focus.
* **In-Page Floating Assist HUD**: Draggable overlay displaying AI recommendations, reasoning, and response latency without altering page state.
* **Visual Vision OCR Cropper**: Capture any on-screen diagram, mathematical equation, or image question and solve it via Multimodal AI (`gemini-3.1-flash-lite`).
* **Markdown Exam Recap Exporter**: Export the entire scanned question set, selected answers, confidence scores, and reasoning to a formatted `.md` file with one click.

### 3. Cloud Serverless AI Pipeline
* **Server-Request-Only Model**: Upstream AI keys never touch the client or extension. All requests route through Vercel Serverless Functions.
* **Dynamic Model-Evaluated Confidence**: AI evaluates its genuine probabilistic certainty score (e.g. `99.2%`, `96.5%`) rather than using static hardcoded templates.
* **Fallback Alternative Suggestions**: Automatically proposes secondary alternative options when model confidence falls below 85%.

### 4. Global Analytics & AI Leaderboard
* **KPI Metrics**: Real-time counters for Global Solves ($142,850+$), Average Response Speed ($0.13\text{s}$), and System Accuracy ($99.4\%$).
* **AI Model Leaderboard**: Ranked table comparing solve volume, latency, and accuracy across active engines.
* **Question Type Breakdown**: Multi-Choice ($82.9\%$), Essay ($10.0\%$), Checkbox ($4.3\%$), Dropdown ($2.0\%$), and Vision OCR ($0.8\%$).
* **Trending Exam Topics**: Frequent topic analysis across Networking/OSI, Linux Administration, SQL, OOP, and Web Protocols.

---

## Supported Platforms

| Platform | Extraction Mode | Auto-Fill / Assist Support |
| :--- | :---: | :---: |
| **Google Forms** | Native Form DOM / Entry IDs | Pre-filled URL & Auto-Fill |
| **Quizizz** | Real-time DOM / Live Packet | Assist Mode (Visual Glow & Reason) |
| **Wayground** | Single-Question Isolation | In-Page Floating HUD Assist |
| **Kahoot / Blooket** | Visual Quiz Cards | Instant Assist Recommendation |
| **Moodle LMS** | Standard Formulation DOM | Option Highlight & Reasoning |
| **Canvas LMS** | Quiz Sortable DOM | Option Highlight & Reasoning |
| **CBT Lokal (Candy / Beesmart)**| Standard Radio / Checkbox DOM | Option Selection & Assist |

---

## Keyboard Shortcuts & Hotkeys

| Shortcut | Action | Scope |
| :--- | :--- | :--- |
| **`F2`** | **Panic Key** (Toggle Floating HUD On / Off) | Browser (Any Quiz Tab) |
| **`Ctrl + Shift + H`** | Alternative Panic Key | Browser (Any Quiz Tab) |
| **`Ctrl + Space`** | Quick Toggle HUD Visibility | Browser (Any Quiz Tab) |

---

## Getting Started & Installation

### A. Running Desktop App
1. Download `HeLLM.exe` from the latest release.
2. Launch `HeLLM.exe`.
3. Enter your **KeyAuth License Key** on the activation screen.
4. Keep the app running in the background (starts local IPC on `127.0.0.1:8765`).

### B. Installing Browser Extension
1. Open your Chromium browser (**Brave**, **Google Chrome**, **Microsoft Edge**).
2. Navigate to `brave://extensions` (or `chrome://extensions`).
3. Enable **Developer mode** in the top-right corner.
4. Click **Load unpacked** and select the `extension/` directory.

---

## Disclaimer

> [!WARNING]
> This software is intended strictly for **educational, academic research, and accessibility assistance purposes**. The developers do not encourage or condone academic dishonesty or misuse on proctored examinations. Use responsibly in accordance with your institution's guidelines and terms of service.

<div align="center">
  <sub>Built with ❤️ by Infernostudios.</sub>
</div>
