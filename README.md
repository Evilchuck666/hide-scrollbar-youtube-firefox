# 🙈 Hide-Scrollbar-YouTube

![Platform](https://img.shields.io/badge/platform-Firefox%20%7C%20Firefox%20for%20Android-blue)
![Firefox](https://img.shields.io/badge/Firefox-%3E%3D140-blue)
![Firefox for Android](https://img.shields.io/badge/Firefox%20for%20Android-%3E%3D142-blue)
[![License](https://img.shields.io/badge/license-GPLv3-green)](LICENSE)
[![Latest release](https://img.shields.io/github/v/release/Evilchuck666/hide-scrollbar-youtube-firefox?label=download&sort=semver)](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/releases/latest)
[![Build and tests](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/actions/workflows/release.yaml/badge.svg?branch=main)](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/actions/workflows/release.yaml)

**Watch YouTube without a scrollbar in the way.**

Hide-Scrollbar-YouTube is a tiny Firefox add-on that hides the page scrollbar
on YouTube video pages. The page still scrolls with the mouse wheel, touchpad
or keyboard; only the bar is gone, so the player and the page use the full
width of the window.

🌐 **Website:** https://evilchuck666.github.io/hide-scrollbar-youtube-firefox/

## ✨ Features

- Runs only on YouTube video pages (`youtube.com/watch…`).
- Hides the scrollbar with a single CSS rule (`scrollbar-width: none`).
- Keeps scrolling working exactly as before.
- Needs no permissions, collects no data and has no settings.

## 📥 Download

| Browser | Latest stable release |
| --- | --- |
| Firefox 140+ | [Download](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/releases/latest/download/hide-scrollbar-youtube.xpi) |

[Release notes](https://github.com/Evilchuck666/hide-scrollbar-youtube-firefox/releases/latest)

## 🚀 Getting started

1. Open the download link above in Firefox.
2. Accept the installation prompt.
3. Open any YouTube video: the scrollbar is gone.

To remove it, go to `about:addons` and uninstall **Hide-Scrollbar-YouTube**.

The `.xpi` published in each release is signed by Mozilla, so it installs in
regular Firefox builds. Firefox updates it only when you install a newer release.

## 🧠 Notes

- YouTube switches pages without reloading. If you open a video from the home
  page or search results, the scrollbar may stay until you reload the video
  page. Once hidden, it stays hidden on other YouTube pages in that tab until
  the next reload.

## 📚 Learn more

- [Technical guide](TECHNICAL_GUIDE.md): source layout, trying the add-on
  locally with `web-ext`, and how releases are signed and published.

## ⚖️ License

Hide-Scrollbar-YouTube is free software released under the **GNU General Public License v3.0** (GPL-3.0). See [LICENSE](LICENSE).
