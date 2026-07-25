<div align="center">

# 📦 GH Store

**A lightweight, self-hosted app store for Android — powered entirely by GitHub Releases.**

Browse, download, and update apps right from your device. No Play Store account, no gatekeepers — just a clean catalog and one-tap installs.

[![Platform](https://img.shields.io/badge/platform-Android-3DDC84?logo=android&logoColor=white)](#)
[![Kotlin](https://img.shields.io/badge/Kotlin-Jetpack%20Compose-7F52FF?logo=kotlin&logoColor=white)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](#license)
[![Powered by](https://img.shields.io/badge/powered%20by-GitHub%20API-181717?logo=github&logoColor=white)](#)

</div>

---

## ✨ Overview

**GitHub Release Store** is a browsable, Play Store–style catalog for apps distributed via GitHub Releases. It keeps track of the latest release for each app in its catalog, and lets you download and install APKs directly to your device — with update notifications whenever a newer release ships.

Perfect for personal projects, internal tools, side projects, or any collection of apps you'd rather not push through an official app store.

<p align="center">
  <em>📸 Screenshots coming soon — check back after the next release!</em>
</p>

---

## 🚀 Features

- **📋 Curated app catalog** — a clean, browsable list of apps, always kept in sync with their latest release
- **🔄 Automatic release detection** — tracks the latest release (version, notes, publish date, and APK) for every app in the catalog
- **⚡ Smart caching** — cached locally with Room; only refetches data older than a configurable interval, so it stays fast and light on API usage
- **🔑 Built-in rate-limit handling** — supports a GitHub Personal Access Token (raises the API limit from 60 to 5,000 requests/hour), with graceful fallback and clear in-app messaging if the limit is ever hit
- **⬇️ Native in-app downloads** — no dependency on the system Download Manager; real-time progress, cancel support, and precise error messages, all inside the app
- **📂 Downloads visible to the user** — files are saved to the public Downloads folder, so they can be found and deleted from any file manager, no "Clear app data" required
- **🆙 Update detection** — compares installed app versions against the latest GitHub release and flags updates automatically
- **🗂️ Dedicated Updates screen** — see every pending update in one place, with a one-tap **Update All** flow (downloads are batched automatically; installs are confirmed one at a time, per Android's security model)
- **🎨 Custom branding** — ships with its own launcher icon and identity

---

## 🧰 Tech Stack

| Layer | Choice |
|---|---|
| Language | Kotlin |
| UI | Jetpack Compose |
| Local storage | Room |
| Networking | Retrofit / OkHttp |
| Image loading | Coil |
| Secure storage | Android Security Crypto (EncryptedSharedPreferences) |

---

## 📖 How It Works

1. The app keeps a catalog of apps up to date behind the scenes, checking for new releases automatically and caching results locally so browsing stays fast and responsive.

2. Tap any app to view its details, release notes, and version history.

3. Download the APK — with live progress, right inside the app — then install it in one tap.

4. Head to the **Updates** tab any time to see everything that's out of date and update it all in one go.

---

## ⚙️ Setup

### 1. (Recommended) Add a GitHub API token

Unauthenticated GitHub API requests are capped at **60/hour**, which is easy to hit as the catalog grows. To raise this to **5,000/hour**:

1. Go to **GitHub → Settings → Developer settings → Personal access tokens**
2. Generate a **fine-grained token**, scoped to read-only access on the relevant repositories
3. Add it in the app's Settings screen — or configure it as a build-time default if you're the sole maintainer

> **Security note:** Never commit a real token into a public repository's source code — anyone can read it directly from the file. Keep token configuration out of version control, or use a scoped, revocable, read-only token if you must.

### 2. Build the app

Open the project and build/run as a normal Android project.

---

## 🔐 Permissions

| Permission | Why it's needed |
|---|---|
| `INTERNET` | Fetching release data and downloading APKs |
| `REQUEST_INSTALL_PACKAGES` | Installing downloaded APKs |

---

## ⚠️ Disclaimer

This project is not affiliated with, endorsed by, or connected to GitHub, Inc. or Google. It simply consumes the public GitHub Releases API. You are responsible for the content, licensing, and safety of any repositories and APKs you choose to list — always vet third-party APKs before installing them, and only add sources you trust.

---

## 📄 License

Distributed under the **MIT License**. See [`LICENSE`](./LICENSE) for details.

---

<div align="center">

Made with ❤️ for developers who just want to ship APKs without the app store hassle.

</div>
